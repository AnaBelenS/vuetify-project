<script lang="ts" setup>
  import HelloWorld from '@/components/HelloWorld.vue'
  import Footer from '@/components/Footer.vue'
</script>

<template>
  <HelloWorld />
  <Footer />
</template>



<!-- <script lang="ts" setup>
  import HelloWorld from '@/components/HelloWorld.vue'
  import Footer from '@/components/Footer.vue'
  import { useAccountStore } from '@/store/account.store';
  import { onBeforeMount } from 'vue';

  const accountStore = useAccountStore();

  onBeforeMount(async ()=>{
    await accountStore.register({
      dni : "2547885D",
      name : "Antonio",
      lastName : "Perez",
      password : "Password_123",
      confrimPassword : "Password_123",
      email : "antonio@gmail.com"
    })
  })

</script>

<template>
  <HelloWorld />
  {{ accountStore.user }}
  <Footer />
</template> -->
