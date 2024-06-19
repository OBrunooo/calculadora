<script setup>
const props = defineProps(['operacao']) 
</script>
<template>
    <label for="operador">Operador</label><br>
    <select id="operador" @change="props.operacao">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="X">X</option>
        <option value="÷">÷</option>
    </select>
</template>
<style scoped>
select {
    width: 100px;
    height: 20px;
    border-radius: 6px;
    margin-bottom: 10px
}

label {
    font-size: 20px;
    margin-right: 5px
}
</style>