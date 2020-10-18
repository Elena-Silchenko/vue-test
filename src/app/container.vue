<template>
  <div class="d-flex">
    <div style="max-width: 20em; width: 20em;">
      <app-sidebar style="max-width: 20em; width: 20em;" />
    </div>
    <app-main class="flex" />
  </div>
</template>

<script>
  import AppSidebar from "./sidebar"
  import AppMain from "./main"

  export default {
    components: {
      "app-sidebar": AppSidebar,
      "app-main": AppMain,
    }
  }
</script>