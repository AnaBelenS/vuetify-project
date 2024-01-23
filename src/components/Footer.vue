<script lang="ts">
  export default {
    data: () => ({
      icons: [
        'mdi-facebook',
        'mdi-twitter',
        'mdi-linkedin',
        'mdi-instagram',
      ],
    }),
  }
</script>

<template>
  <v-footer class="d-flex flex-column bg-grey-lighten-5">
    <div class="bg-pink-lighten-5 d-flex w-100 align-center px-4">
      <strong>Get connected with us on social networks!</strong>

      <v-spacer />

      <v-btn
        v-for="icon in icons"
        :key="icon"
        class="mx-4"
        :icon="icon"
        variant="plain"
        size="small"
      ></v-btn>
    </div>

    <div class="px-4 py-2 bg-grey-lighten-5 text-center w-100">
      {{ new Date().getFullYear() }} — <strong>PincelART</strong>
    </div>
  </v-footer>
</template>


