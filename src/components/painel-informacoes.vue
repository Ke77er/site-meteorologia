<template>
        <div class="container">
  <div class="column">
    <div class="square">Temperatura</div>
    <div class="square">Umidade</div>
  </div>
  <div class="column">
    <div class="square">Sensação térmica</div>
    <div class="square">Vento Km/h</div>
  </div>
  <div class="column">
    <div class="square">Chuva (mm)</div>
    <div class="square">Ponto de Orvalho</div>
  </div>
</div>
</template>

<script>
export default {
  name: 'painelInformacoes',
}
</script>

<style>
.container {
  display: flex;
  justify-content: space-between;
}

.column {
padding-top: 30px;
  flex: 1;
  margin: 0 35px;
}

.square {
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  background-image: radial-gradient(rgb(238, 215, 173), rgb(151, 98, 0));
  margin: 20px 0;
  border-radius: 5px;
}
</style>