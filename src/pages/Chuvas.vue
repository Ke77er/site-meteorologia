<template>
    <main-layout>
      <historico-chuvas/>
    </main-layout>
  </template>
  
  <script>
    import MainLayout from '../layouts/Main.vue'
    import historicoChuvas from '../components/chuvas/chuvas-historico.vue'
  
    export default {
      components: {
        MainLayout,
        historicoChuvas
      }
    }
  </script>
  