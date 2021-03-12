<template>
  <div class="conversor">
    <h2>{{moedaA}} para {{moedaB}}</h2>
    <div class="inputs">
      <input class="input-value" type="text" v-model="moedaA_value" v-bind:placeholder="moedaA">
      <input class="button" type="button" value="Converter" v-on:click="converter">
    </div>
    
    <h2>{{moedaB_value}}</h2>
  </div>
</template>

<script>
export default {
  name: "Conversor",
  props: ["moedaA", "moedaB"],
    data(){
      return{
        moedaA_value: "",
        moedaB_value: 0
      };
    },
    methods: {
      converter(){
        let de_para = this.moedaA + "_" + this.moedaB;

        let url = "https://free.currconv.com/api/v7/convert?q="+ de_para +"&compact=ultra&apiKey=30ddbf79cb78978487f1";

        fetch(url)
          .then(res => {
            return res.json();
          })
          .then(json => {
            let cotacao = json[de_para];
            this.moedaB_value = (cotacao * parseFloat(this.moedaA_value)).toFixed(3);
          });  
      }
    }
}
</script>

<style scoped>
.conversor {
  padding: 20px;
  max-width: 350px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0);

  background: #2F2F2F;
  border-radius: 5px;
}

.input-value {
  width: 120px;
  height: 34px;
  border: none;
  border-radius: 8px 0 0 8px
}

.inputs {
  display: flex;
  justify-content: center;
  align-items: center;
}

.button {
  background: #68A047;
  color: white;
  font-family: 'Source Sans Pro', sans-serif;
  font-size: medium;

  width: 80px;
  height: 36.5px;
  border: none;
  border-radius: 0px 8px 8px 0;

  transition: background-color 0.2s;
}

.button:hover {
  background: #538038;
}

</style>
