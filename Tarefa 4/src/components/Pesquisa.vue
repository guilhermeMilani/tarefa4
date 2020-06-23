<template>
  <fieldset>
    <h1>DETRAN</h1>
    <label for="placa">Informe a Placa:</label>
    <input type="text" id="placa"  maxlength="8" v-model="placa" />
    <button @click="pesquisarVeiculo">Pesquisar</button>
  </fieldset>
</template>

<script>
export default {
  data: function() {
    return {
      placa: ""
    };
  },
  methods: {
    pesquisarVeiculo: function() {       
      this.$store.state.infracoesVeiculo = this.$store.state.multas.filter(
        multa => multa.PLACA == this.placa
      );
      this.$router.push("/infracoes")
    }
  }
};
</script>

<style>
html, body{
  background: rgb(2,0,36);
background: linear-gradient(90deg, rgba(2,0,36,1) 0%, rgba(23,180,131,1) 50%, rgba(0,212,255,1) 100%);
}
fieldset {
    height: 300px;
    width: 400px;
    margin: 50px 36%;
    text-align: center;
    border: transparent;
}
button{
  margin: 0 10px;
}
label{
  margin: 0 10px;
}
input{
  width: 150px;
}
</style>