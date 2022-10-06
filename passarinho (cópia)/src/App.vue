<template>
  <div class="container my-5">
    <CadastrarRecado @recadoCadastradoMS="cadastrar"> </CadastrarRecado>
    <ListarRecados :recadosProp="recados"> </ListarRecados>
  </div>
</template>

<script>

import axios from "axios";
import CadastrarRecado from "./components/CadastrarRecado.vue";
import ListarRecados from "./components/ListarRecados.vue";

export default {
  name: "App",
  components: {
    CadastrarRecado,
    ListarRecados,
  },
    data(){
        return {
            recados: ['a', 'b', 'c', 'd'],
            
        }
    },
    methods : {
      cadastrar(recado) { 
        this.recados.push(recado);
      },

      buscarMensagens() {
        axios.get('http://192.100.60.125:8080/RestAPI/rest/recados').then((resultado)=> {
          console.log(resultado); //! NAO RETIRAR, ISSO PERMITE QUE TUDO FUNCIONE.
        }).catch((erro) => {
          console.log(erro);
      });
      } //*fim do metodo buscar
    }
};
</script>

<style scoped>

</style>