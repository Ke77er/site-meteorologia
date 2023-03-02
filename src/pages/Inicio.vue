<template>
  <main-layout>
    <painelInformacoes/>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue'
  import painelInformacoes from '../components/inicio/inicio-informacoes.vue'

  export default {
    components: {
      MainLayout,
      painelInformacoes
    }
  }
</script>
<style>
</style>
