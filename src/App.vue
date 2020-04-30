<template>
  <v-app>
    <AppBar />
    <v-content>
      <Home />
      <About />
      <Features />
      <Vita />
      <!-- <References /> -->
      <Contact />
    </v-content>
    <Footer />
  </v-app>
</template>

<script>
import AppBar from './components/AppBar'
import Home from './components/Home'
import About from './components/About'
import Features from './components/Features'
import Vita from './components/Vita'
//import References from './components/References'
import Contact from './components/Contact'
import Footer from './components/Footer'

export default {
  name: 'App',

  components: {
    AppBar,
    Home,
    About,
    Features,
    Vita,
    //References,
    Contact,
    Footer,
  },
  data: () => ({}),
}
</script>
