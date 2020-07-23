<template>
  <v-app>
    <Sidebar/>
    <Footer/>
  </v-app>
</template>

<script>
  import Sidebar from "./components/Sidebar"
  import Footer from "./components/footer"
  export default {
    name: 'App',

    components: {
      Sidebar,
      Footer,
    }
  }
</script>
