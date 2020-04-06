<template>
  <section id="vita">
    <div class="py-12">
      <v-container class="text-center">
        <h2 class="display-2 font-weight-bold mb-3" data-aos="zoom-in">
          VITA
        </h2>

        <v-responsive class="mx-auto mb-8" width="56">
          <v-divider class="mb-1"></v-divider>

          <v-divider></v-divider>
        </v-responsive>

        <v-responsive>
          <v-timeline :align-top="false">
            <v-timeline-item
              v-for="(item, i) in items"
              :key="i"
              :color="item.color"
              :icon="item.icon ? item.icon : 'mdi-plus'"
              :data-aos="i % 2 == 0 ? 'fade-left' : 'fade-right'"
            >
              <span slot="opposite">{{ item.from }} - {{ item.to }}</span>
              <v-card class="elevation-2">
                <v-card-title class="headline">{{ item.title }}</v-card-title>
                <v-card-text>
                  {{ item.text }}
                </v-card-text>
              </v-card>
            </v-timeline-item>
          </v-timeline>
        </v-responsive>
      </v-container>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: 'mdi-school',
          from: '2006',
          to: '2012',
          title: 'Qualifikation Oberstufe',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          icon: 'mdi-calendar-month',
          from: '2012',
          to: '2014',
          title: 'Fachhochschulreife',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          icon: 'mdi-calendar-month',
          from: '2014',
          to: '2017',
          title: 'Ausbildung',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          icon: 'mdi-xml',
          from: 'Juni 2018',
          to: 'April 2020',
          title: 'Werkstudent',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        },
        {
          icon: '',
          from: '2017',
          to: 'heute',
          title: 'Studium',
          text:
            'Lorem ipsum dolor sit amet, no nam oblique veritus. Commune scaevola imperdiet nec ut, sed euismod convenire principes at. Est et nobis iisque percipit, an vim zril disputando voluptatibus, vix an salutandi sententiae.'
        }
      ]
    }
  }
}
</script>

<style></style>
