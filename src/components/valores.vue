<script setup>
    const props = defineProps(['n1valor', 'n2valor'])
</script>
<template>
    <h1>CALCULADORA</h1>
    <div class="num1">
        <label for="num1">1° Número: </label>
        <input id="num1" type="number" @keyup="props.n1valor" >
    </div>
    <div class="num2">
        <label for="num2">2° Número: </label>
        <input id="num2" type="number" @keyup="n2valor">
    </div>
</template>
<style scoped>
    input, select{
        width: 100px;
        height: 20px;
        border-radius: 6px;
        margin-bottom: 10px
        }

        label{
        font-size: 20px
        }
</style>