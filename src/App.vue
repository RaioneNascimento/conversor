<template>
  <div id="app">
    <h1 class="title">Conversor de Moedas</h1>
    <div class="linha">
      <Conversor moeda-a="USD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="USD" />
    </div>    
    <div class="linha">
      <Conversor moeda-a="CAD" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="CAD" />
    </div>
    <div class="linha">
      <Conversor moeda-a="EUR" moeda-b="BRL" />
      <Conversor moeda-a="BRL" moeda-b="EUR" />
    </div>
  </div>
</template>

<script>
import Conversor from  "./components/Conversor"
export default {
  name: "app",
  components: {
    Conversor
  }
};
</script>

<style>
html, 
body {
    margin: 0;
    padding: 0;
    background-color: #363636;
}
#app {
  margin: auto;
  margin-top: 60px;
  max-width: 900px;
  font-family: 'Recursive', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  
  color: white;
}

.linha {
  margin-top: 40px;

  display: flex;
  justify-content: space-around;
}

.title {
  text-align: center ;
}
</style>
