<template>
  <div class="container">
    <div class="row">
      
      <div class="col-md-4">
      
      </div>
      <!-- fim da imagem -->

      <div class="col-md-7">

            <h1>Cálculo de pedaços de pizza necessários.</h1>
            <p>
             PIZZAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAA!
            </p>

            <div class="mb-3">
              <label class="form-label">Quantidade de Crianças: </label>
              <input class="form-control" type="text" v-model="kid" />
            </div>
            <div>
              <label class="form-label">Quantidade de Adultos:</label>
              <input class="form-control" type="text" v-model="adult"/>
            </div>
          
          <button v-on:click="calcular()"> PIZZAS? </button>

      </div>
<!-- aqui acaba o form. -->
    </div>

    <div class="row">
      <div class="offset-md-4 col-md-8">
        <!-- mostrar resultado -->

        <div>
          <p> {{piz12}} pizzas de 12 necessárias.  </p>
          <p> {{piz10}} pizzas de 10 necessárias.  </p>
          <p> {{piz8}} pizzas de 8 necessárias.  </p>
          <p> e precisaria de {{pzzcomplem}} pizza complementar de 8 pedaços, sobrando {{cmpltleft}}</p>

</div>
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
    kid: 0,
    adult: 0,
     qntd_adul: 0,
     qntd_kid: 0,
     piz12: 0,
     piz10: 0,
     piz8: 0,
     lftvr: 0,
     pzzcomplem: 0,
     cmpltleft: 0
}
},
//!calculações.
methods : {

 calcular(){
  this.piz12 = 0;
  this.piz10 = 0;
     this.piz8 = 0;
     this.lftvr = 0;
     this.pzzcomplem = 0;
     this.cmpltleft = 0;
  let lftvr;
 this.qntd_adul =  this.adult * 3;
    this.qntd_kid = this.kid * 2;
let pieces = (this.qntd_adul) + (this.qntd_kid);

/*Dividindo o total de pedaços por 12 para saber quantas pizzas de 12; dividimos o resto por 10 e por 8 para 
* saber quantas pizzas dos outros (10 e 8) teremos. Se o resto for maior que 0, somamos 1 pizza mais 
* para que não falte.
*/ 
this.piz12 = parseInt(pieces / 12);
            this.lftvr = pieces % 12;
            this.piz10 = parseInt(this.lftvr / 10);
            this.lftvr = this.lftvr % 10;

            this.piz8 = parseInt(this.lftvr / 8);
            this.lftvr = this.lftvr % 8;
            if(this.lftvr > 0) {
              this.pzzcomplem = 1;
              this.cmpltleft = 8 - this.lftvr;
            }
          
}
}
}
</script>

<style scoped>
</style>