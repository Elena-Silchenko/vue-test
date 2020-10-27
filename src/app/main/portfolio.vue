<template>
  <div ref="gallery" class="d-flex" style="position: relative; width: 100%; height: 15em; overflow-x: hidden;" @mouseenter="speed = 30" @mouseleave="speed = 10">
    <img ref="images" v-for="image in gallery" :src="image.url" :key="image.url" :style="{ left: image.left + 'px' }" @load="image.width = image.ref.clientWidth" />
  </div>
</template>

<script>
  function image(url) {
    return { url: url, left: 0, width: 0, ref: null }
  }

  const gallery = [
    image("./images/portfolio-1.jpg"),
    image("./images/portfolio-2.jpg"),
    image("./images/portfolio-3.jpg"),
    image("./images/portfolio-4.jpg"),
    image("./images/portfolio-5.jpg"),
    image("./images/portfolio-6.jpg"),
  ]

  export default {
    data: () => ({
      height: 0,
      gallery: gallery,
      shift: 0,
      speed: 10
    }),

    mounted() {
      this.gallery.forEach((img, index) => {
        img.ref = this.$refs.images[index]
      })
      this.adjustShift()
    },

    methods: {
      adjustShift() {
        requestAnimationFrame(() => {
          this.shift--
          let x = this.shift
          let move = false
          this.gallery.forEach(img => {
            let width = img.width + 20

            img.left = x
            if(x < -width) {
              move = true
            }
            x += width
          })

          if(move) {
            this.shift += this.gallery[0].width + 20
            this.gallery.push(this.gallery.shift())
          }

          setTimeout(() => {
            this.adjustShift()
          }, this.speed)
        })
      }
    }
  }
</script>

<style scoped lang="scss">
  img {
    max-height: 15em;
    margin-right: 1em;
    position: absolute;
    top: 0;
  }
</style>