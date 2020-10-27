<template>
  <div class="sidebar" :class="{ fixed: scrollY > startScroll }">
    <div v-for="link in links" :key="link.href">
      <a :href="link.href">{{ link.title }}</a>
    </div>
  </div>
</template>

<script>
  function link(href, title) {
    return { href: href, title: title }
  }

  const links = [
    link("#about", "About"),
    link("#portfolio", "Portfolio"),
    link("#contact", "Contact"),
    link("#price", "Price")
  ]

  export default {
    data: () => ({
      links: links,
      scrollY: 0,
      startScroll: 0
    }),

    mounted() {
      this.startScroll = this.$el.offsetTop - 30
      window.addEventListener("scroll", this.checkScroll)
      this.checkScroll()
    },

    methods: {
      checkScroll() {
        this.scrollY = window.scrollY
      }
    }
  }
</script>

<style scoped lang="scss">
  .sidebar {
    padding-left: 2em;

    & > div {
      padding-bottom: 1em;

      & > a {
        color: #000;
        text-decoration: none;

        &:hover {
          color: var(--blue);
        }
      }
    }

    &.fixed {
      position: fixed;
      top: 30px;
    }
  }
</style>

<style>
  :root {
    --blue: #6200ea;
  }
</style>