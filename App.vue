<template>
<adultos> </adultos>
<kids> </kids>
</template>

<script>
import Adultos from '/home/lab/Área de Trabalho/frameworks3TDS/pizzometro/src/components/Adultos.vue'
import Kids from '/home/lab/Área de Trabalho/frameworks3TDS/pizzometro/src/components/Kids.vue'
export default {
 name : 'app',
 components: {
Adultos, 
Kids
  },
  data(){
    return{ //! Como demonios faço esto????
      kidss : 0,
      adultoss : 0,
      qnt_Ped_Adul : 0,
      qnt_Ped_Kid : 0
    }
  },//TODO Metodos, nenhum funciona. Arrumar depois.
 method : {
  calcular() {
  this.qnt_Ped_Adul = adulto * 3;
    this.qnt_Ped_Kid = kids * 3;


  }
 } 
}
</script>

<style>

</style>
