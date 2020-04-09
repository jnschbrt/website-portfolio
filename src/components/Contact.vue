<template>
  <section>
    <!-- <v-sheet id="contact" color="#333333" dark tag="section" tile> -->
    <v-img height="800" src="../assets/contact_bg.jpg">
      <div class="py-12"></div>

      <v-container>
        <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">
          Kontakt
        </h2>

        <v-responsive class="mx-auto mb-12" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-theme-provider>
          <v-row>
            <v-col class="text-right mr-8">
              <!-- <h1 class="display-2 font-weight-light	">Impressum</h1>
              <p class="font-weight-thin">Angaben gemäß § 5 TMG:</p>

              <p class="font-weight-light">
                <span class="font-weight-bold">Jonas Schubert</span> <br />
                Weststraße 49 <br />
                48282 Emsdetten <br />
              </p>
              <p class="font-weight-light">
                <span class="font-weight-light"> E-Mail:</span>
                schubert.jonas@web.de
              </p> -->
            </v-col>

            <v-col cols="6">
              <v-card elevation="3">
                <v-card-text>
                  <v-form ref="form" v-model="valid">
                    <v-text-field
                      label="Ihr Name"
                      type="text"
                      filled
                      clearable
                      color="blue-grey darken-4"
                      background-color="white"
                      prepend-icon="mdi-email"
                    ></v-text-field>
                    <v-text-field
                      label="Ihre E-Mail Adresse"
                      type="email"
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
                    color="blue-grey darken-4"
                    block
                  >
                    Senden
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
        </v-theme-provider>
      </v-container>

      <div class="py-12"></div>
    </v-img>
    <!-- </v-sheet> -->
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
