<!-- 1 -->
<template>
  <div class="container">
    <div class="row">
      
      <div class="col-md-4">
        <img alt="Vue logo" src="./assets/wesley.png" />
      </div>
      <!-- fim da imagem -->

      <div class="col-md-7">

            <h1>Cálculo de % de anjo</h1>
            <p>
              Em 2015 uma obra prima da música foi lançada. <b>Aquele 1%</b> é a
              música que por meio de uma matemática sofistica calcula seu valor de
              anjo perfeito.
            </p>

            <div class="mb-3">
              <label class="form-label">dia:</label>
              <input class="form-control" type="text" v-model="dia" />
            </div>
            <div>
              <label class="form-label">mês:</label>
              <input class="form-control" type="text" v-model="mes"/>
            </div>
            <div>
              <label class="form-label">ano:</label>
              <input class="form-control" type="text" v-model="ano" />
            </div>

          <button v-on:click="calcular()"> calcular </button>

      </div>
      <!-- fim do formulário -->

    </div>

    <div class="row">
      <div class="offset-md-4 col-md-8">
        <!-- area para exibir as variáveis -->

        <div v-if="dia != 1 && anjeza == 0">
          <p> processando... </p></div>

          <div v-if="anjeza != 0 && nao_anjeza != 0">
          <p> {{anjeza}} % anjo perfeito, mas aquele {{nao_anjeza}} % vagabundo. </p>
          </div>


        <br> 
       
      </div>
    </div>

  </div>
</template>

<!-- 2 -->
<script>

export default {

name: 'app',
data(){
  return {
    dia: null,
    mes: null,
    ano: null,
    anjeza: 0,
    nao_anjeza: 0
}
},
methods : {

  somatorio(mes) {
    let soma = 0;
    let repeticoes = mes;
    for(let i = 0; i < repeticoes; i++){
      soma = soma + mes;
      mes--;
    }


    return soma;
  },

  calcular(){

    if(this.ano >= 2000) {
      this.ano = this.ano - 2000;
    }else if(this.ano > 1000) {
      this.ano = this.ano - 1900;
    }
    this.nao_anjeza = this.somatorio(parseInt(this.mes)) + (this.ano/100) * (50-this.dia);
    this.anjeza = 100 - this.nao_anjeza;
    this.anjeza = Math.round(this.anjeza); 
        this.nao_anjeza = Math.round(this.nao_anjeza); 
  }
}
}

</script>
<!-- 3-->
<style scoped>

</style>