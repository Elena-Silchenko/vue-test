<template>
  <v-app>
    <app-header />
    <app-container />
    <app-footer />
  </v-app>
</template>

<script>
  import AppHeader from "@/header"
  import AppContainer from "@/container"
  import AppFooter from "@/footer"

  export default {
    components: {
      "app-header": AppHeader, 
      "app-container": AppContainer,
      "app-footer": AppFooter,
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }
</style>
