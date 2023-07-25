<template>
    <div class="post">
        <h3>{{ props.title }}</h3>
        <p>{{ props.content }}</p>
        <input type="text" v-model="message">
        <button @click="handleClick">Saludar</button>
    </div>
</template>

<script lang="ts" setup>
import { Ref, ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
    title: {
        type: String,
        required: true
    },
    content: {
        type: String,
        required: false,
        default: "Este post no tiene contenido"
    }
});

const emit = defineEmits(["sayHi"]);

const handleClick = () => {
    emit("sayHi", "Hola");
};

let message: Ref<string> = ref("");

</script>

<style scoped>
.post {
    width: 15rem;
    height: 15rem;
    background-color: antiquewhite;
    border-radius: .8rem;
    margin: .8rem;
    padding: .8rem;
}
</style>