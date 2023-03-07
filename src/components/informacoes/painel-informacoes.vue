<template>
<div class="containerinf">
  <div class="column">
    <div class="square">
      <img src="src\icons\termometro.png" alt="">
      <p>Temperatura</p>
    </div>
    <div class="square">
      <img src="src\icons\gotas.png" alt="">
      <p>Umidade</p>
    </div>
  </div>
  <div class="column">
    <div class="square">
      <img src="src\icons\termico.png" alt="">
      <p>Sensação térmica</p>
    </div>
    <div class="square">
      <img src="src\icons\ventoso.png" alt="">
      <p>Vento Km/h</p>
    </div>
  </div>
  <div class="column">
    <div class="square">
      <img src="src\icons\chuva-leve.png" alt="">
      <p>Chuva (mm)</p>
    </div>
    <div class="square">
      <img src="src\icons\folha.png" alt="">
      <p>Ponto de Orvalho</p>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'painelInformacoes',
}
</script>

<style>
img {
  width: 40px;
  height: 40px;
}

.containerinf {
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
  padding-bottom: 100%;
  background-image: radial-gradient(rgb(238, 215, 173), rgb(151, 98, 0));
  border-radius: 5px;
  margin: 5px;
  border: 2px solid black;
}
.square img {
  float: left;
  margin-right: 10px;
}
</style>