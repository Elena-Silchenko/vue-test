<template>
  <v-row style="padding: 3em 0;">
    <price-card v-for="card in priceList"
      :key="card.id"
      :id="card.id"
      :name="card.name"
      :cost="card.cost"
      :features="card.features"
    />
  </v-row>
</template>

<script>
  import PriceCard from "./price-card"

  export default {
    data: () => ({
      priceList: [
        {
          id: "basic",
          name: "Basic",
          cost: 9.95,
          features: ["f1", "f2"],
        },
        {
          id: "advanced",
          name: "Advanced",
          cost: 14.95,
          features: ["f2", "f3"],
        },
        {
          id: "premium",
          name: "Premium",
          cost: 49.95,
          features: ["f1", "f2", "f3", "f4"],
        },
      ]
    }),

    components: {
      "price-card": PriceCard,
    }
  }
</script>