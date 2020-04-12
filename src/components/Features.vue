<template>
  <section id="features" class="grey lighten-3">
    <div class="py-12"></div>

    <v-container class="text-center">
      <h2 class="display-2 font-weight-bold mb-3" data-aos="fade-down">
        DIENSTLEISTUNGEN
      </h2>

      <v-responsive class="mx-auto mb-12" width="56">
        <v-divider class="mb-1"></v-divider>

        <v-divider></v-divider>
      </v-responsive>

      <v-row>
        <v-col v-for="(feature, i) in features" :key="i" cols="12" md="4">
          <v-card
            class="py-12 px-4"
            color="grey lighten-5"
            height="475"
            :data-aos="feature.animation ? feature.animation : ''"
          >
            <v-theme-provider dark>
              <div>
                <v-avatar color="#01d28e" size="88">
                  <v-icon x-large v-text="feature.icon"></v-icon>
                </v-avatar>
              </div>
            </v-theme-provider>

            <v-card-title
              class="justify-center font-weight-black text-uppercase"
              v-text="feature.title"
            ></v-card-title>

            <v-card-text class="subtitle-1" v-text="feature.text">
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>

    <div class="py-12"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          icon: 'far fa-comments',
          title: 'Beratung',
          text:
            'Eine fachliche Beratung ist in Zeiten von schier unendlichen Web-Technologien und Frameworks unerlässlich. In engen Kundengesprächen werden kundenspezifische und problemorientierte Lösungsansätze entworfen.',
          animation: 'fade-right'
        },
        {
          icon: 'mdi-ruler-square-compass',
          title: 'Konzeption',
          text:
            'Erfolgreiche und ansprechende Websites benötigen eine durchdachte und logische Struktur. Aus gegebenen Lösungsansätzen werden Struktur, Inhalte und Navigation abgeleitet.',
          animation: 'fade-up'
        },
        {
          icon: 'mdi-file-code-outline',
          title: 'Entwicklung',
          text:
            'Moderne und benutzerfreundliche Applikationen erfordern den Einsatz neuster Web-Technologien. Jahrelange Ausbildung, Erfahrungen in unterschiedlichsten Technologien und Frameworks und eine best-practice-orientierte Arbeitsweise schaffen eine erfolgreiche Entwicklung.',
          animation: 'fade-left'
        }
      ]
    }
  }
}
</script>

<style></style>
