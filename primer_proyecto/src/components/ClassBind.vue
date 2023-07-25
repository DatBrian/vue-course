<template>
    <p v-bind:style="{ backgroundColor: '#ccc', color: color }">Colores XD</p>
    <button @click="handleClick()">Cambiar color</button>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

let color: Ref<string> = ref('#fff');

const handleClick = (): void => { color.value = '#ff0000' }

</script>

<style scoped></style>