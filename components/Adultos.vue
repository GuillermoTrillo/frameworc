<template>
   <div> 
    <input type="number" name="adulto" v-model='adultovar'> A
  </div>
 <p> {{adulto}} </p>
</template>

<script>

export default {
   name : 'Adultos',
    data(){
        return{
        adultovar : 0
        }
    }
}
</script>

<style scoped>

</style>
