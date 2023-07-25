<template>
    <h2>Recorrer Array</h2>
    <ul>
        <li v-for="(country, index) in countriesArray" v-bind:key="index">{{ country }}</li>
    </ul>
    <h2>Recorrer Objetos</h2>
    <ul class="object-list">
        <li v-for="country in countriesObject" v-bind:key="country.code">{{ country.name }}</li>
    </ul>
</template>

<script lang="ts" setup>

import { Ref, ref } from 'vue';
let countriesArray: Ref<Array<string>> = ref([
    'Spain', 'France', 'UK', 'Italy', 'Portugal'
]);

interface I_Country {
    code: string,
    name: string
}

let countriesObject: Ref<Array<I_Country>> = ref([
    {
        code: 'es',
        name: 'Spain',
    },
    {
        code: 'fr',
        name: 'France',
    },
    {
        code: 'it',
        name: 'Italy',
    }
])

</script>

<style scoped></style>