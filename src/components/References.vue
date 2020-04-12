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
          <v-flex xs12 sm6 md4 lg4 v-for="(item, i) in references" :key="i">
            <v-card class="ma-3" max-width="600" elevation="2">
              <v-card-text> {{ item.text }}</v-card-text>
              <v-card-actions>
                <span class="body-2 font-weight-light">
                  - {{ item.title }}</span
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
          title: 'Referenz 1',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          title: 'Referenz 2',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          title: 'Referenz 3',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          title: 'Referenz 4',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          title: 'Referenz 5',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          title: 'Referenz 6',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        }
      ]
    }
  }
}
</script>

<style></style>
