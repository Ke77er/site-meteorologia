<template>
    <main-layout>
      <div class="map">mapa</div>
    </main-layout>
  </template>
  
  <script>
    import MainLayout from '../layouts/Main.vue'
    export default {
      components: {
        MainLayout
      }
    }
  </script>
  <style>
  .map {
    display: flex;
    justify-content: center;
    align-self: center;
    width: 600px;
    height: 400px;
    border: 2px solid black;
    margin: 0 17%;
  }
  </style>
  