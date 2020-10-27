<template>
  <v-row style="padding: 3em 0;">
    <v-card class="mx-auto" max-width="400" elevation="10" outlined tile>

      <v-card-title>Basic</v-card-title>

      <v-card-subtitle>&euro; 4,95</v-card-subtitle>

      <v-card-text>
        <v-list class="transparent">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-marked-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Feature 1</v-list-item-title>
            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-blank-outline</v-icon>
            </v-list-item-icon>

            <v-list-item-title>Feature 2</v-list-item-title>

            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
        </v-list>
      </v-card-text>

      <v-divider class="mx-4" />

      <v-card-actions>
        <v-btn
          color="deep-purple lighten-2"
          text
          @click="reserve">
          Order Now
        </v-btn>
      </v-card-actions>
    </v-card>

    <v-card class="mx-auto" max-width="400" elevation="10" outlined tile>

      <v-card-title>Advanced</v-card-title>

      <v-card-subtitle>&euro; 19,95</v-card-subtitle>

      <v-card-text>
        <v-list class="transparent">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-marked-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Feature 1</v-list-item-title>
            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-blank-outline</v-icon>
            </v-list-item-icon>

            <v-list-item-title>Feature 2</v-list-item-title>

            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
        </v-list>
      </v-card-text>

      <v-divider class="mx-4" />

      <v-card-actions>
        <v-btn
          color="deep-purple lighten-2"
          text
          @click="reserve">
          Order Now
        </v-btn>
      </v-card-actions>
    </v-card>

    <v-card class="mx-auto" max-width="400" elevation="10" outlined tile>

      <v-card-title>Premium</v-card-title>

      <v-card-subtitle>&euro; 49,95</v-card-subtitle>

      <v-card-text>
        <v-list class="transparent">
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-marked-outline</v-icon>
            </v-list-item-icon>
            <v-list-item-title>Feature 1</v-list-item-title>
            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
          <v-list-item>
            <v-list-item-icon>
              <v-icon>mdi-checkbox-blank-outline</v-icon>
            </v-list-item-icon>

            <v-list-item-title>Feature 2</v-list-item-title>

            <v-list-item-subtitle class="text-right">
              description
            </v-list-item-subtitle>
          </v-list-item>
        </v-list>
      </v-card-text>

      <v-divider class="mx-4" />

      <v-card-actions>
        <v-btn
          color="deep-purple lighten-2"
          text
          @click="reserve">
          Order Now
        </v-btn>
      </v-card-actions>
    </v-card>
  </v-row>
</template>