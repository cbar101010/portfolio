<template>
  <v-app>
    <Sidebar/>
  </v-app>
</template>

<script>
  import Sidebar from "./components/Sidebar"
  export default {
    name: 'App',

    components: {
      Sidebar
    }
  }
</script>
