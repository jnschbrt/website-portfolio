<template>
  <section id="about-me">
    <div class="py-12"></div>

    <v-container class="text-center">
      <h2 class="display-2 font-weight-bold mb-3" data-aos="fade-down">
        ÜBER MICH
      </h2>

      <v-responsive class="mx-auto mb-8" width="56">
        <v-divider class="mb-1"></v-divider>

        <v-divider></v-divider>
      </v-responsive>

      <v-responsive
        class="mx-auto title font-weight-light mb-8"
        max-width="720"
        data-aos="fade-right"
      >
        <p>
          Hi! 👋🏻Ich bin Jonas Schubert, ein {{ this.age }} Jahre alter
          Full-Stack-Developer aus dem Münsterland. Während meines
          Wirtschaftsinformatik Studiums an der Fachhochschule Münster, meinen
          Tätigkeiten als Werkstudent und meiner Ausbildung als Fachinformatiker
          für Anwendungsentwicklung lernte ich den Umgang mit neusten und
          modernsten Frameworks und Plattformen des Web- und
          Software-Engineerings.
        </p>
        <p>Scrollt und erfahrt mehr über mich und meine Arbeit.</p>
      </v-responsive>

      <v-avatar class="elevation-12 mb-8" size="200" data-aos="zoom-in">
        <v-img
          src="../assets/portrait_bw.jpg"
          alt="portrait"
          position="top"
        ></v-img>
      </v-avatar>

      <v-row justify="space-around" class="mb-4">
        <div class="group mb-8">
          <a
            v-for="icon in icons"
            :key="icon.icon"
            :href="icon.link"
            target="_blank"
          >
            <v-tooltip bottom>
              <template v-slot:activator="{ on }">
                <v-icon x-large class="mx-3 hvr-grow" v-on="on">
                  {{ icon.icon }}</v-icon
                >
              </template>
              <span>{{ icon.tooltip }}</span>
            </v-tooltip>
          </a>
        </div>
      </v-row>

      <v-btn
        class="white--text font-weight-black hvr-grow"
        color="#01d28e"
        rounded
        large
        @click="$vuetify.goTo('#contact')"
      >
        Get in touch
      </v-btn>
    </v-container>

    <div class="py-12"></div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      age: 0,
      icons: [
        {
          icon: 'mdi-github',
          link: 'https://github.com/Lizzal',
          tooltip: 'GitHub'
        },
        {
          icon: 'mdi-twitter',
          link: 'https://twitter.com/_jnschbrt',
          tooltip: 'Twitter'
        },
        {
          icon: 'mdi-xing',
          link: 'https://www.xing.com/profile/Jonas_Schubert10/cv',
          tooltip: 'XING'
        },
        {
          icon: 'mdi-linkedin',
          link: 'https://www.linkedin.com/in/schubert-jonas',
          tooltip: 'LinkedIn'
        }
      ]
    }
  },
  created() {
    const birthday = new Date('1996, 06, 06')
    var ageDifMs = Date.now() - birthday.getTime()
    var ageDate = new Date(ageDifMs)
    this.age = Math.abs(ageDate.getUTCFullYear() - 1970)
  }
}
</script>

<style scoped>
/* Grow */
.hvr-grow {
  display: inline-block;
  vertical-align: middle;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px rgba(0, 0, 0, 0);
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -webkit-transition-property: transform;
  transition-property: transform;
}
.hvr-grow:hover,
.hvr-grow:focus,
.hvr-grow:active {
  -webkit-transform: scale(1.1);
  transform: scale(1.1);
}
</style>
