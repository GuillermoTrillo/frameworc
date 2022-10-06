<template>
    <div class="listar-recados">

        <div v-for="(recado, index) in recadosProp" :key="index" class="recado">
                {{recado}}
            
        </div>

    </div>
</template>

<script>
export default {
    name : 'ListarRecados',
    props: {
        recadosProp : Array
    }

}
</script>

<style scoped>
.listar-recados {
    display: flex;
}

.recado {
    width: 250px;
    border: solid 1px #ccc;
    border-radius: 5px;;
    padding: 25px;
}
</style>
