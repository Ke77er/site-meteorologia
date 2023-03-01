<template>
    <div class="cidades-container">
      
      <button v-for="cidade in cidadesFiltradas" :key="cidade" class="cidades">{{ cidade }}</button>
    </div>
  </template>
  
  <script>
  export default {
    name: 'locaisMeteorologia',
    props: {
    filtro: {
      type: String,
      default: '',
    },
  },
    data() {
      return {
        cidades: ['Rio de Janeiro', 'Rio Grande', 'Rio Grande do Norte', 'Panambi', 'Goias', 'Sergipe', 'Maceió', 'São Paulo', 'Belo Horizonte', 'Brasília', 'Salvador', 'Recife', 'Fortaleza', 'Curitiba', 'Porto Alegre', 'Manaus'],
      }
    },
    computed: {
    cidadesFiltradas() {
      // filtra a lista de cidades com base no valor da propriedade "filtro"
      return this.cidades.filter(cidade => cidade.toLowerCase().includes(this.filtro.toLowerCase()))
    }
  },
}
  </script>

  <style>
  .cidades-container {
  height: 100%;
}
  .cidades{
    border-radius: 5px;
    width: 100%;
    height: 50px;
    padding: 5px;
    background-image: radial-gradient(rgb(238, 215, 173),orange);
  }

</style>