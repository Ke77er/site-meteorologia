<template>
  <div class="wrapper">
    <div class="search-container">
      <input type="text" placeholder="Pesquisar" v-model="filtro" @input="filtrarCidades">
      <div class="left-div">
        <locaisMeteorologia :filtro="filtro"/>
      </div>
    </div>
    <div class="divisao">
      <br><br>
    <div class="container">
      <ul class="navli">
        <li class="navbar">
          <v-link class="vlink" href="/">Inicio</v-link>
          <v-link class="vlink" href="/informacoes">Informações</v-link>
          <v-link class="vlink" href="/chuvas">Chuvas</v-link>
          <v-link class="vlink" href="/graficos">Graficos</v-link>
          <v-link class="vlink" href="/mapa">Mapa</v-link>
        </li>
      </ul>
    </div>
      <div class="right-div">
        <slot></slot>
      </div>
      <footer>Rodapé da Div</footer>
    </div>
  </div>
</template>

<script>
import painelInformacoes from '../components/inicio/inicio-informacoes.vue'
import locaisMeteorologia from '../components/locais-meteorologia.vue'
import historicoChuvas from '../components/chuvas/chuvas-historico.vue'
  import VLink from '../components/VLink.vue'

  export default {
    components: {
      VLink,
      painelInformacoes,
      locaisMeteorologia,
      historicoChuvas
      
    },
  data() {
    return {
      filtro: '',
    }
  },
  methods: {
    filtrarCidades() {
      // chamada de método vazia para acionar a atualização da lista de cidades no componente "locaisMeteorologia"
    }
  }
}
</script>

<style scoped>
  .wrapper {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    max-width: 100%;
    height: 93vh; 
    margin: 0 auto;
    padding: 15px 30px;
    background-image: radial-gradient(rgb(238, 215, 173), rgb(151, 98, 0));
  }
  .divisao{
    width: 69%;
    display: inline-block;
  }
  .search-container {
    width: 29%;
    display: flex;
    flex-direction: column;
  }
  .search-container input {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
    box-sizing: border-box;
  }
  .left-div {
    height: 654px;
    background-image: radial-gradient(rgb(238, 215, 173), rgb(151, 98, 0));
    margin-top: 30px;
    overflow-y: auto;
    border-radius: 5px;
  }
  .right-div {
    flex: 1 1 100%;
    height: 564px;
    background-image: radial-gradient(rgb(238, 215, 173), rgb(151, 98, 0));
    margin-top: 30px;
    border-radius: 5px;
  }
  .container {
    text-align: center;
    justify-content: space-between;
    flex: 1 1 70%;
    margin-right: 20px;
  }
  .vlink {
    border: 2px solid black;
    border-radius: 5px;
    border-color: black;
    margin: auto;
  }
  .navli {
    list-style:none;
    display:inline;
  }
  footer {
    position: relative;
  bottom: 0;
  left: 0;
  right: 0;
  height: 70px;
  width: 971px;
  background-color: #44321b;
  text-align: center;
}
</style>
