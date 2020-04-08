<template>
  <v-app-bar fixed color="transparent" hide-on-scroll elevation="0">
    <v-layout class="d-flex flex-row-reverse">
      <v-btn
        v-for="(link, i) in links"
        :key="i"
        @click="$vuetify.goTo(link.to)"
        text
        class="white--text font-medium subtitle-1	"
      >
        {{ link.text }}
      </v-btn>
    </v-layout>
  </v-app-bar>
</template>

<script>
// import { headroom } from 'vue-headroom'
export default {
  components: {
    // headroom
  },
  data() {
    return {
      links: [
        { to: '#about-me', text: 'Über mich' },
        { to: '#vita', text: 'Vita' },
        { to: '#contact', text: 'Kontakt' }
      ]
    }
  }
}
</script>

<style></style>
