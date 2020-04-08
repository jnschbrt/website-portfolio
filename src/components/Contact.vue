<template>
  <v-sheet id="contact" color="#333333" dark tag="section" tile>
    <div class="py-12"></div>

    <v-container>
      <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">
        Contact Me
      </h2>

      <v-responsive class="mx-auto mb-12" width="56">
        <v-divider class="mb-1"></v-divider>

        <v-divider></v-divider>
      </v-responsive>

      <v-form ref="form" v-model="valid">
        <v-theme-provider light>
          <v-row>
            <v-col cols="6">
              <v-text-field
                label="Name"
                filled
                clearable
                color="black"
                background-color="white"
              ></v-text-field>
              <v-text-field
                label="Email"
                filled
                clearable
                color="black"
                background-color="white"
              ></v-text-field>
              <v-text-field
                label="Betreff"
                filled
                clearable
                color="black"
                background-color="white"
              ></v-text-field>
            </v-col>

            <v-col cols="6">
              <v-textarea
                label="Ihre Nachricht"
                filled
                clearable
                color="black"
                background-color="white"
                height="228"
                no-resize
              ></v-textarea>
            </v-col>

            <v-col class="mx-auto" cols="auto">
              <v-btn
                class="white--text font-weight-bold hvr-grow"
                color="blue lighten-1"
                large
              >
                Nachricht senden
              </v-btn>
            </v-col>
          </v-row>
        </v-theme-provider>
      </v-form>
    </v-container>

    <div class="py-12"></div>
  </v-sheet>
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
