<template>
  <main-layout>
    <painelInicio/>
  </main-layout>
</template>

<script>
  import MainLayout from '../layouts/Main.vue'
  import painelInicio from '../components/inicio/painel-inicio.vue'

  export default {
    components: {
      MainLayout,
      painelInicio
      
    }
  }
</script>
<style>
</style>
