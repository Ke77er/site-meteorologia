<template>
  <div class="cidades-cont">
    <button v-for="(cidade, index) in cidadesFiltradas" :key="cidade" class="cidades">
      {{ cidade }}
    <span>1/3</span>
    </button>
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
  .cidades-cont {
    height: 100%;
  }
  .cidades span {
    margin-left: auto;
  }
  .cidades{
    display: flex;
    justify-content: space-between;
    align-items: center;
    text-align: center;
    border-radius: 5px;
    width: 100%;
    height: 50px;
    padding: 5px;
    background-image: radial-gradient(rgb(238, 215, 173),orange);
  }
</style>