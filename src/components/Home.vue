<template>
  <v-parallax src="../assets/parralax.jpg" height="786">
    <v-row align="center" justify="center" class="mt-12 pt-12">
      <v-col class="text-center mt-12 pt-12" cols="12">
        <h1
          class="font-weight-bold mb-2"
          :class="[$vuetify.breakpoint.smAndDown ? 'display-3' : 'display-4']"
        >
          Jonas Schubert
        </h1>
        <h2
          class="font-weight-thin"
          :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
        >
          Full-Stack-Developer
        </h2>
      </v-col>
    </v-row>
    <v-row>
      <div class="scroll-downs" @click="$vuetify.goTo('#about-me')">
        <div class="mousey">
          <div class="scroller"></div>
        </div>
      </div>
    </v-row>
  </v-parallax>
</template>

<script>
export default {}
</script>

<style scoped>
#bg-image {
  background: rgba(0, 0, 0, 0.7);
}

.scroll-downs {
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  margin: auto;

  width: 34px;
  height: 55px;
}
.mousey {
  width: 3px;
  padding: 10px 15px;
  height: 35px;
  border: 2px solid #fff;
  border-radius: 25px;
  opacity: 0.75;
  box-sizing: content-box;
}
.scroller {
  width: 3px;
  height: 10px;
  border-radius: 25%;
  background-color: #fff;
  animation-name: scroll;
  animation-duration: 2.2s;
  animation-timing-function: cubic-bezier(0.15, 0.41, 0.69, 0.94);
  animation-iteration-count: infinite;
}
@keyframes scroll {
  0% {
    opacity: 0;
  }
  10% {
    transform: translateY(0);
    opacity: 1;
  }
  100% {
    transform: translateY(15px);
    opacity: 0;
  }
}
</style>
