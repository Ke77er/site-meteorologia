<template>
  <main-layout>
    <painelInformacoes/>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue'
  import painelInformacoes from '../components/painel-informacoes.vue'

  export default {
    components: {
      MainLayout,
      painelInformacoes
    }
  }
</script>
<style>
</style>
