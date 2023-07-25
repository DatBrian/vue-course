<template>
    <h3>{{ counter }}</h3>
    <button @click="addCounter">Incrementaar</button>
</template>

<script lang="ts" setup>

import { Ref, ref } from 'vue';
let counter: Ref = ref(0);
const addCounter = (): void => {
    counter.value++;
}

</script>