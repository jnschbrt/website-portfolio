<template>
  <section id="vita">
    <div class="py-12"></div>

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
            color="#01d28e"
            :icon="item.icon ? item.icon : 'mdi-plus'"
            :data-aos="i % 2 == 0 ? 'fade-left' : 'fade-right'"
          >
            <span slot="opposite">{{ item.from }} - {{ item.to }}</span>
            <v-card class="elevation-2">
              <v-card-title class="headline">{{ item.title }}</v-card-title>
              <v-card-text class="text-justify">
                {{ item.text }}
              </v-card-text>
            </v-card>
          </v-timeline-item>
        </v-timeline>
      </v-responsive>
    </v-container>
    <div class="py-12"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: 'mdi-school',
          from: '2012',
          to: '2014',
          title: 'Fachhochschulreife',
          text:
            'Im Juni 2011 verlies ich die Maximilian-Kolbe-Gesamtschule in Saerbeck mit der Fachhochschulreife.'
        },
        {
          icon: 'mdi-account-arrow-left',
          from: '2014',
          to: '2017',
          title: 'Ausbildung Wilken Software Group',
          text:
            'Im August 2014 begann ich meine Ausbildung bei der Wilken Software Group GmbH. Im Rahmen der Ausbildung beschäftigte ich mich primär mit der Entwicklung im Bereich Microsoft Dynamic Navision und der Schnittstellenentwicklung. Im Juli 2017 schloss ich die Ausbildung zum Fachinformatiker für Anwendungsentwicklung mit der Abschlussnote 2,0 ab.'
        },
        {
          icon: 'fa-university',
          from: '2017',
          to: 'heute',
          title: 'Studium',
          text:
            'Im Oktober 2017 begann ich mein Studium im Bereich Wirtschaftsinformatik an der Fachhochschule Münster.'
        },
        {
          icon: 'mdi-xml',
          from: 'Juni 2018',
          to: 'April 2020',
          title: 'Werkstudent Wilken Software Group',
          text:
            'Nach Abschluss der Ausbildung unterstützte ich die Entwicklungsabteilung weiterhin als Werkstudent bei der Entwicklung von Modulen und Tools der Microsoft Dynamics NAV Branchenlösung und bei der Beratung/Schulung von Kunden des Energieversorgersektors.'
        },
        {
          icon: 'mdi-server-security',
          from: 'August 2020',
          to: 'Oktober 2020',
          title: 'Praktikum Ernst & Young',
          text:
            'In einem dreimonatigen Praktikum bei der Ernst & Young GmbH Wirtschaftsprüfungsgesellschaft als IT Consultant für IT Audit / IT Prüfung, sammelte ich weitere wertvolle Erfahrungen im Berateralltag und prüfte IT Systeme auf Sicherheitsrisiken im Rahmen der Wirtschaftsprüfung.'
        },
        {
          icon: 'mdi-code-braces',
          from: 'Mai 2020',
          to: 'heute',
          title: 'Werkstudent ZEB',
          text:
            'Neben meinem Bachelorstudium bin ich als Full-Stack-Developer bei der zeb.rolfes.schierenbeck.associates gmbh tätig. '
        }
      ]
    }
  }
}
</script>

<style></style>
