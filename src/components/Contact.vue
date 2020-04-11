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
              v-model="valid"
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
                filled
                clearable
                color="blue-grey darken-4"
                background-color="white"
                prepend-icon="mdi-email"
              >
              </v-text-field>

              <v-text-field
                label="Ihre E-Mail Adresse"
                type="email"
                name="email"
                filled
                clearable
                color="blue-grey darken-4"
                prepend-icon="mdi-email"
                background-color="white"
              >
              </v-text-field>

              <v-textarea
                label="Ihre Nachricht"
                filled
                clearable
                type="text"
                name="message"
                color="blue-grey darken-4"
                counter="400"
                prepend-icon="mdi-email"
                background-color="white"
                no-resize
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
              @submit.prevent
            >
              Senden
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-theme-provider>
    </v-container>
  </section>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    name: '',
    nameRules: [
      v => !!v || 'Name is required',
      v => (v && v.length <= 10) || 'Name must be less than 10 characters'
    ],
    email: '',
    emailRules: [
      v => !!v || 'E-mail is required',
      v => /.+@.+\..+/.test(v) || 'E-mail must be valid'
    ],
    select: null,
    items: ['Item 1', 'Item 2', 'Item 3', 'Item 4'],
    checkbox: false
  }),

  methods: {
    validate() {
      this.$refs.form.validate()
    },
    reset() {
      this.$refs.form.reset()
    },
    resetValidation() {
      this.$refs.form.resetValidation()
    }
  }
}
</script>

<style></style>
