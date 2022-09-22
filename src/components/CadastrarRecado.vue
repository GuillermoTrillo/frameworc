<template>
    <div class="input-group mb-3">
  <input type="text" class="form-control" placeholder="Digite seu recado"  v-model="recado">
  <button class="btn btn-outline-secondary" type="button" id="button-addon2">Button</button>
<br>
</div>
<p>caracteres restante: <b> {{120 - recado.length}} </b> </p>

</template>

<script>
export default {
    name : 'CadastrarRecado',
    data() {
        return {
        recado : ''
        }
    }
}
</script>

<style scoped>
@import url('https://cdn.jsdelivr.net/npm/bootstrap@5.2.1/dist/css/bootstrap.min.css');
</style>
