<template>
  <v-app-bar app hide-on-scroll class="app-bar">
    <v-avatar class="mr-3" color="grey lighten-5">
      <v-img contain max-height="70%" src="/assets/portrait_bw.jpg"></v-img>
    </v-avatar>

    <v-toolbar-title class="headline">
      Jonas Schubert
    </v-toolbar-title>
  </v-app-bar>
</template>

<script>
export default {}
</script>

<style>
.app-bar {
  height: 70px;
  background: transparent;
  border: none;
  transition: background-color 0.3s;
  will-change: transform;
}
</style>
