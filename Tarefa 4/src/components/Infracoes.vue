<template>
  <div class="infracoes">
        <div v-for="(infracao, index) in infracoes" :key="index">
        <label class="txt1" for="data">Data da infração:</label>
        <input type="text" id="data" :value="infracao.DADOS_INFRACAO.DATAHORA" /><br>

        <label class="txt2" for="placa">Placa:</label>
        <input type="text" id="placa" :value="infracao.PLACA" /><br>

        <label class="txt3" for="placa">Localidade:</label>
        <input type="text" id="placa" :value="infracao.LOCALIDADE" /><br>

        <label class="txt4" for="placa">Tipo:</label>
        <input type="text" id="placa" :value="infracao.DADOS_INFRACAO.TIPO" /><br>

        <label class="txt5" for="placa">Valor:</label>
        <input type="text" id="placa" :value="infracao.DADOS_INFRACAO.VALOR" /><br>

        <h4 id="texto" v-if="infracao.DADOS_INFRACAO.TIPO == 'VELOCIDADE'"> Velocidade Máxima: {{infracao.DADOS_INFRACAO.VEL_MAXIMA}}</h4>
        <button id="botao" @click="voltar">Consultar outra Placa</button>

  </div>
        

  </div>
</template>

<script>
export default {
  computed: {
    infracoes: function() {
        return this.$store.state.infracoesVeiculo
    }  
  }, methods:{
    voltar: function(){
      this.$router.push("/")
    }
  }
};
</script>

<style>
.txt1{
  color:white
}
.txt2{
  color:white
}
.txt3{
  color:white
}
.txt4{
  color:white
}
.txt5{
  color:white
}
#texto{
  color: red;
}
.infracoes{
margin: 110px 0px 0px 545px;
}
</style>