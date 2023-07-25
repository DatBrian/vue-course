<template>
    <section>
        <h3>Añadir profesor</h3>
        <div>
            <label>Nombre:</label>
            <input type="text" v-model="teacher.name">
        </div>
        <div>
            <label>Apellidos:</label>
            <input type="text" v-model="teacher.surname">
        </div>
        <div>
            <label>DNI:</label>
            <input type="text" v-model="teacher.dni">
        </div>
        <div>
            <label>Materias:</label>
            <input type="text" v-model="subject">
            <button @click="handleSubject()">Añadir Materia</button>
        </div>
        <div>
            <ul>
                <li v-for="(subj, index) in teacher.subjects" v-bind:key="index">{{ subj }}</li>
            </ul>
        </div>
        <input type="checkbox" v-model="teacher.doc">Documentación entregada
        <button @click="handleAddTeacher()">Agregar</button>
    </section>

    <section>
        <h3>Listado de profesores</h3>
        <table>
            <tr>
                <th>Nombre</th>
                <th>Apellidos</th>
                <th>DNI</th>
                <th>Materias</th>
                <th>Documentación</th>
            </tr>
            <tr v-for="teacher in teachers" :key="teacher.dni">
                <th>{{ teacher.name }}</th>
                <th>{{ teacher.surname }}</th>
                <th>{{ teacher.dni }}</th>
                <th>
                    <ul>
                        <li v-for="(subject, index) in teacher.subjects" :key="index">{{ subject }}</li>
                    </ul>
                </th>
                <th v-if="teacher.doc">Documentación entregada</th>
                <th v-else>Documentación no entregada</th>
            </tr>
        </table>
    </section>
</template>

<script lang="ts" setup>
import { Ref, ref } from 'vue';

interface ITeacher {
    name: string,
    surname: string,
    dni: number,
    subjects: Array<string>,
    doc: boolean
}

let teacher: Ref<ITeacher> = ref({
    name: '',
    surname: '',
    dni: '',
    subjects: [],
    doc: false
});

let teachers: Ref<Array<ITeacher[]>> = ref([

]);

let subject: Ref<string> = ref('');

const handleSubject = (): void => {
    teacher.value.subjects.push(subject.value);
    subject.value = '';
}

const handleAddTeacher = (): void => {
    teachers.value.push({ ...teacher.value });

    teacher.value = {
        name: '',
        surname: '',
        dni: '',
        subjects: [],
        doc: false,
    };

}

</script>

<style scoped></style>