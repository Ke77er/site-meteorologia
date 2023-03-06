<template>
  <div class="cidades-cont">
      <button v-for="(cidade, index) in cidadesFiltradas" :key="cidade" class="cidades">
        {{ cidade }}
        <span>1/3</span>
        <button @click="renomearCidade(index)">Editar</button>
        <button @click="excluirCidade(index)">Excluir</button>
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
        indicesExpandidos: [1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1, 1],
      }
    },
    computed: {
    cidadesFiltradas() {
      // filtra a lista de cidades com base no valor da propriedade "filtro"
      return this.cidades.filter(cidade => cidade.toLowerCase().includes(this.filtro.toLowerCase()))
    }
  },
  methods: {
    renomearCidade(index) {
      const novaCidade = prompt('Digite o novo nome da cidade:');
      if (novaCidade) {
        this.cidades.splice(index, 1, novaCidade);
      }
    },
    excluirCidade(index) {
      if (confirm(`Deseja realmente excluir ${this.cidades[index]}?`)) {
        this.cidades.splice(index, 1);
      }
    },
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