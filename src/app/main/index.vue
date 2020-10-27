<template>
  <v-main>
    <v-container>
      <div style="padding: 2em; background: #f3f3f3;">
        <app-about />
        <app-portfolio class="mb-5" />
        <app-contact class="mb-5"/>
        <app-price />
      </div> 
    </v-container>
  </v-main>
</template>

<script>
  import AppAbout from "./about"
  import AppPortfolio from "./portfolio"
  import AppContact from "./contact"
  import AppPrice from "./price"

  export default {
    components: {
      "app-about": AppAbout,
      "app-portfolio": AppPortfolio,
      "app-contact": AppContact,
      "app-price": AppPrice
    }
  }
</script>