<template>
    <main-layout>
      <painelInformacoes/>
    </main-layout>
  </template>
  <script>
    import MainLayout from '../layouts/Main.vue'
    import painelInformacoes from '../components/informacoes/painel-informacoes.vue'
  
    export default {
      components: {
        MainLayout,
        painelInformacoes
      }
    }
  </script>