<template>
  <v-card class="mx-auto" max-width="280" elevation="10" outlined tile style="position: relative;">
    <v-card-title class="d-flex justify-space-between">
      <div>
        {{ name }}
      </div>

      <div class="badge">
        &euro; {{ cost | round }},<sup>{{ cost | modulo }}</sup>
      </div>
    </v-card-title>

    <v-card-text>
      <v-list class="transparent">
        <v-list-item v-for="feature in Features" :key="feature.id">
          <v-list-item-icon>
            <v-icon v-if="features.indexOf(feature.id) >= 0">mdi-checkbox-marked-outline</v-icon>
            <v-icon v-else>mdi-checkbox-blank-outline</v-icon>
          </v-list-item-icon>
          <v-list-item-title>{{ feature.title }}</v-list-item-title>
          <v-list-item-subtitle class="text-right">
            {{ feature.description }}
          </v-list-item-subtitle>
        </v-list-item>
      </v-list>
    </v-card-text>

    <v-divider class="mx-4" />

    <v-card-actions>
      <v-btn
        color="deep-purple lighten-2"
        text
        @click="order()">
        Order Now
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
  const Features = [
    {
      id: "f1",
      title: "Feature 1",
      description: "Some description of feature 1",
    },
    {
      id: "f2",
      title: "Feature 2",
      description: "Some description of feature 2",
    },
    {
      id: "f3",
      title: "Feature 3",
      description: "Some description of feature 3",
    },
    {
      id: "f4",
      title: "Feature 4",
      description: "Some description of feature 4",
    },
  ]

  export default {
    props: {
      id: String,
      name: String,
      cost: Number,
      features: Array,
    },

    data: () => ({
      Features: Features,
    }),

    filters: {
      round(value) {
        return Math.floor(value)
      },

      modulo(value) {
        return Math.round(100 * (value - Math.floor(value)))
      }
    },

    methods: {
      order() {
        alert(this.id)
      }
    }
}
</script>

<style lang="scss" scoped>
  .badge {
    color: #fff;
    position: absolute;
    top: 0;
    right: 0;
    background: var(--blue);
    border-radius: 50%;
    height: 5em;
    width: 5em;
    align-items: center;
    display: flex;
    justify-content: center;
    transform: translate(-10%, -55%);
    text-shadow: 1px 1px #523679;
  }
</style>