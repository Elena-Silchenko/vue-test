<template>
  <div>
    <v-layout align-center row wrap pa-3>
      <div class="overflow-y-hidden" style="height: 2.3em;">
        <img :src="`./images/logo.png`" style="height: 3em;" />
      </div>

      <v-flex text-center>
        "Neque porro quisquam est qui dolorem ipsum"
      </v-flex>
    </v-layout>

    <div class="progress" ref="progress" :class="{ fixed: scrollY > startScroll }">
      <!-- div class="progress-actual" ref="progressActual" :style="{ width: progress + '%' }" /-->
      <div class="progress-actual" ref="progressActual" :style="{ width: `${progress}%` }" />
    </div>
  </div>
</template>

<script>
export default {
  data: () => ({
    scrollY: 0,
    startScroll: 0,
    progress: 0,
  }),

  mounted() {
    this.startScroll = this.$refs.progress.offsetTop
    window.addEventListener("scroll", this.checkScrolling)
    this.checkScrolling()
  },

  methods: {
    checkScrolling() {
      this.scrollY = window.scrollY

      this.progress = 100 * window.scrollY / (document.body.clientHeight - window.innerHeight)
    }
  }
}
</script>

<style scoped lang="scss">
  .progress {
    height: 2px;
    background: transparent;
    position: relative;

    &.fixed {
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 9999;
    }

    .progress-actual {
      background: red;
      position: absolute;
      top: 0;
      left: 0;
      height: 100%;
    }
  }
</style>