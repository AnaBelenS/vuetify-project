<script lang="ts">
import Products from "./Products.vue"
  export default {
    name: 'HelloWorld',
    components: {Products},
    data: () =>({
      product: [
           {id: 1},
           {id: 2},
           {id: 3},
      ]
    })
  }
</script>

<template>

  <v-card-text>
      <v-row>
        <v-col cols="12" md="4" sa="6" v-for="(row, index) in product" :key="index">
          <products>
          </products>
      </v-col>
      </v-row>
    </v-card-text>
</template>



