<template>
   <div> 
    <input type="number" name="kids" v-model='kids'> E
    <p> {{kids}}</p>
  </div>

</template>

<script>

export default {
   name : 'Kids',
    data(){
        return{
        kids : 0
        }
    }
}
</script>

<style scoped>

</style>
