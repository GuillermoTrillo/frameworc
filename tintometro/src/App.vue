<template>

    <h1> Tinte Loja: Compre Agora  para ser feliz! </h1>

    <br> <br>

  
    <div>
      <p> Quanta área, em metros quadrados, você planeja pintar?</p>
      <input type="number" v-model="area">
      <button v-on:click='calcular()'>Calcular</button>
    </div>
    <div>
      <p>A quantidade de latas de 18 litros necessários seria: {{l18}}</p>
      <p>A quantidade de galôes de 3,6 litros necessários seria: {{g36}}</p>
      <p>Valor perfeito, usando só o necessário: R${{final}},00</p>
      <br>

      <p>Quantidade final só com 18 litros: {{qntdL}} </p>
     <p>Valor final com só 18 litros: R${{finalL}},00 </p> <br>

      <p>Quantidade final só com 3,6 litros: {{qntdG}} </p>
      <p>Valor final com só 3,6 litros: R${{finalG}},00</p>

    </div>
 
</template>

<script>
export default {
  name: 'App',
  data(){
    return{
      area: 0,
      g36: 0,
      l18: 0,
      final: 0,
      finalL: 0,
      qntdL: 0,
      finalG: 0,
      qntdG: 0
    }
  },
  methods:{
    calcular(){
     let litro = this.area/6;
     let litroL = this.area/6;
     let litroG = this.area/6;
    //Para a letra A:

   this.finalL =  80 * Math.round(litroL / 18);
this.qntdL = litroL /18 ;

if(this.finalL < 80 && this.finalL > 0) {
    this.finalL = 80;
    }

    //Para a letra B:
   this.finalG =  25 * Math.floor(litroG / 3.6);
this.qntdG = litroG / 3.6;

    //Para o desafio do professor:
     if(litro%18==0){
        this.l18 = litro/18;
        this.g36 = 0;
        this.final = this.l18*80;
      }
      else if(litro%18!=0){
        this.l18 = Math.floor(litro/18);
        this.g36 = Math.ceil((litro%18)/3.6);
        this.final = (this.l18*80)+(this.g36*25);
      }
    }
  }
}
</script>

<style scoped>

</style>