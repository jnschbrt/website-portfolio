<template>
  <section id="contact">
    <div class="py-12"></div>

    <v-container class="text-center">
      <v-theme-provider>
        <v-card elevation="3">
          <v-card-subtitle>GET IN TOUCH</v-card-subtitle>
          <v-card-title class="justify-center">
            <h2>Kontakt</h2>
          </v-card-title>
          <v-card-text>
            <v-form
              ref="form"
              name="contact"
              method="post"
              data-netlify="true"
              data-netlify-honeypot="bot-field"
            >
              <!-- For netlify, against spam -->
              <input type="hidden" name="form-name" value="contact" />

              <v-text-field
                label="Ihr Name"
                type="text"
                name="name"
                v-model="name"
                required
                :error-messages="nameErrors"
                filled
                clearable
                color="#01d28e"
                background-color="white"
                prepend-icon="mdi-email"
                @input="$v.name.$touch()"
                @blur="$v.name.$touch()"
              >
              </v-text-field>

              <v-text-field
                label="Ihre E-Mail Adresse"
                type="email"
                name="email"
                v-model="email"
                required
                :error-messages="emailErrors"
                filled
                clearable
                color="#01d28e"
                prepend-icon="mdi-email"
                background-color="white"
                @input="$v.email.$touch()"
                @blur="$v.email.$touch()"
              >
              </v-text-field>

              <v-textarea
                label="Ihre Nachricht"
                filled
                clearable
                type="text"
                name="message"
                v-model="message"
                required
                :error-messages="messageErrors"
                color="#01d28e"
                counter="500"
                prepend-icon="mdi-email"
                background-color="white"
                no-resize
                @input="$v.message.$touch()"
                @blur="$v.message.$touch()"
              >
              </v-textarea>
            </v-form>
          </v-card-text>
          <v-card-actions>
            <v-btn
              class="white--text font-weight-bold"
              color="#01d28e"
              block
              type="submit"
              @click="submit"
            >
              Senden
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-theme-provider>
    </v-container>
    <v-snackbar
      v-model="snackbar"
      :timeout="snackbarTimeout"
      bottom
      right
      color="#01d28e"
      class="white--text font-weight-bold"
    >
      {{ snackbarText }}
      <v-btn
        class="white--text font-weight-light"
        text
        @click="snackbar = false"
      >
        Close
      </v-btn>
    </v-snackbar>
  </section>
</template>

<script>
import axios from 'axios'
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'

export default {
  mixins: [validationMixin],

  validations: {
    name: { required },
    email: { required, email },
    message: { required, maxLength: maxLength(500) }
  },

  data: () => ({
    name: '',
    email: '',
    message: '',
    snackbar: false,
    snackbarText: 'Nachricht gesendet',
    snackbarTimeout: 6000
  }),

  computed: {
    nameErrors() {
      const errors = []
      if (!this.$v.name.$dirty) return errors
      !this.$v.name.required && errors.push('Bitte wählen Sie Ihren Namen')
      return errors
    },
    emailErrors() {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Keine gültige E-Mail')
      !this.$v.email.required &&
        errors.push('Bitte wählen Sie eine E-Mail Adresse')
      return errors
    },
    messageErrors() {
      const errors = []
      if (!this.$v.message.$dirty) return errors
      !this.$v.message.maxLength &&
        errors.push('Die Nachricht darf nicht mehr als 500 Zeichen umfassen')
      !this.$v.message.required &&
        errors.push('Bitte geben Sie Ihre Nachricht ein')
      return errors
    }
  },

  methods: {
    submit() {
      this.$v.$touch()
      if (this.$v.$invalid) {
        // when form is invalid
        return
      }

      // form valid
      var form = {
        name: this.name,
        email: this.email,
        message: this.message
      }

      // post form to netlify
      const axiosConfig = {
        header: { 'Content-Type': 'application/x-www-form-urlencoded' }
      }
      axios.post(
        '/',
        this.encode({
          'form-name': 'contact',
          ...form
        }),
        axiosConfig
      )

      this.snackbar = true

      // clear form
      this.$v.$reset()
      this.name = ''
      this.email = ''
      this.message = ''
      form = {}
    },
    encode(data) {
      return Object.keys(data)
        .map(
          key => `${encodeURIComponent(key)}=${encodeURIComponent(data[key])}`
        )
        .join('&')
    }
  }
}
</script>

<style></style>
