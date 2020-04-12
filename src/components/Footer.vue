<template>
  <v-footer color="#313131" padless height="200" class="align-end">
    <v-row justify="center" no-gutters>
      <v-btn
        v-for="icon in icons"
        :key="icon"
        class="mx-4 white--text"
        icon
        x-large
        :href="icon.link"
        target="_blank"
      >
        <v-icon size="24px">{{ icon.icon }}</v-icon>
      </v-btn>
      <v-col
        class="py-4 text-center white--text"
        justify="space-start"
        cols="12"
      >
        <div class="font-weight-light grey--text text--lighten-1 text-center">
          &copy; {{ new Date().getFullYear() }} — Made with
          <v-icon small class=" grey--text">mdi-heart-outline</v-icon>
          , a lot of
          <v-icon small class=" grey--text">mdi-coffee-outline</v-icon>
          and a bit
          <v-icon small class=" grey--text">mdi-vuetify</v-icon>
          by Jonas Schubert
        </div>
      </v-col>
    </v-row>
  </v-footer>
</template>

<script>
export default {
  data: () => ({
    icons: [
      {
        icon: 'fab fa-github',
        link: 'https://github.com/Lizzal',
        tooltip: 'GitHub'
      },
      {
        icon: 'fab fa-twitter',
        link: 'https://twitter.com/_jnschbrt',
        tooltip: 'Twitter'
      },
      {
        icon: 'fab fa-xing',
        link: 'https://www.xing.com/profile/Jonas_Schubert10/cv',
        tooltip: 'XING'
      },
      {
        icon: 'fab fa-linkedin',
        link: 'https://www.linkedin.com/in/schubert-jonas',
        tooltip: 'LinkedIn'
      }
    ]
  })
}
</script>

<style></style>
