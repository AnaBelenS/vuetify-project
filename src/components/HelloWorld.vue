<script setup lang="ts">
import { ref } from "vue";

import { useAccountStore } from "@/store/account.store";

const accountStore = useAccountStore();

const valid = ref(true);
const formRef = ref<HTMLFormElement>();

const validateForm = async (): Promise<void> => {
  console.log('llega') //comprobra si llega aquí borrar
  //Si todo es correcto se envia los datos al backend
  if (formRef.value) {
    const { valid } = await formRef.value.validate()
    if (valid) {
      console.log(accountStore.user)
      await accountStore.register(accountStore.user)
    }
  }
}
const nameRules = [
  (v: string) => !!v || "El nombre es requerido",
  (v: string) =>(v && v.length >= 10) || "El nombre debe tener al menos 10 caracteres",
];



</script>

<template>
  {{ accountStore.user }} <!-- Ver lo que se está guardando -->
  <v-form ref="formRef" v-model="valid" lazy-validation>
    <v-row>
      <v-col sm="6" cols="12">
        <v-text-field
          v-model="accountStore.user.name"
          label="Nombre"
          :rules="nameRules"
        />
      </v-col>
    </v-row>

    <v-row>
      <v-col class="d-flex justify-end">
        <v-btn
          color="secondary"
          @click="validateForm"
        >
          Guardar
        </v-btn>
        <v-btn
          color="accent"
          class="ml-5"
        >
           Volver
        </v-btn>
      </v-col>
    </v-row>
  </v-form>
</template>

<!-- <script lang="ts">
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
</template> -->
