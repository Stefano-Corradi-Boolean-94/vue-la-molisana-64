
<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'


export default {
  name: 'App',
  components:{
    Header,
    Main,
    Footer
  }
}
</script>

<template>

  <Header />

  <Main />

  <Footer />

</template>

<style lang="scss">
// qui includo gli stili generali che verranno ereditati da tutta l'app
// quindi non metto scoped nel tag style

@use './scss/main';


</style>