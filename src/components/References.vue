<template>
  <section id="features" class="grey lighten-3">
    <div class="py-12"></div>

    <v-container class="text-center">
      <h2 class="display-2 font-weight-bold mb-3" data-aos="fade-down">
        REFERENZEN
      </h2>

      <v-responsive class="mx-auto mb-12" width="56">
        <v-divider class="mb-1"></v-divider>

        <v-divider></v-divider>
      </v-responsive>

      <v-responsive>
        <v-layout row wrap class="justify-around">
          <v-flex xs12 sm6 md4 lg6 v-for="(item, i) in references" :key="i">
            <v-card
              class="ma-3"
              max-width="600"
              elevation="2"
              :data-aos="i % 2 == 0 ? 'fade-right' : 'fade-left'"
            >
              <v-card-text class="text-justify"> "{{ item.text }}"</v-card-text>
              <v-card-actions>
                <span class="body-2 font-italic" id="refTitle"
                  >- {{ item.title }}</span
                >
              </v-card-actions>
            </v-card>
          </v-flex>
        </v-layout>
      </v-responsive>
    </v-container>
    <div class="py-12"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      references: [
        {
          title: 'Ausbildungszeugnis Wilken Software Group GmbH',
          text:
            'Herr Schubert bewies während der gesamten Ausbildungsdauer ein überdurchschnittliches Engagement und eine stets sehr gute Auffassungsgabe, aufgrund derer er sich extrem rasch auf neue Ausbildungsinhalte einstellen konnte. Er konnte daher sehr schnell effektiv in Arbeitsabläufe eingebunden werden. Auch bei hohen Belastungen bewältigte er seine Aufgaben stets termingerecht und zu unserer vollen Zufriedenheit.'
        },
        {
          title: 'Praktikumszeugnis Ernst & Young',
          text:
            'Herr Schubert identifizierte sich stets gut mit seinen Aufgaben und zeichnete sich durch eine stets hohe Lern- und Arbeitsmotivation aus. Er war ein stets zuverlässig und selbstständig arbeitender Praktikant. Herr Schubert verfügt über ein gutes analytisches Denkvermögen. Auch bei schwierigen Aufgaben stellte er seine Leistungsfähigkeit jederzeit unter Beweis. Bei seiner Arbeit erzielte er in qualitativer und quantitativer Hinsicht stets gute bis sehr gute Ergebnisse.'
        }
      ]
    }
  }
}
</script>

<style scoped>
#refTitle {
  color: #01d28e;
}
</style>
