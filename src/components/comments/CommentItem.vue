<template>
    <div class="card"> 
        <span>
            <h3>#{{ props.id + 1 }}</h3>
        <h3>{{props.date}}</h3>
        </span>
        <h2>{{ props.title }}</h2>
        <h3>{{ props.body }}</h3>
        <button v-on:click="clicked()">Click me!</button>
        <button v-on:click="actPro()">Soy una Actividad Pro</button>
    </div>
</template>
<script setup lang="ts">
import type { IComment } from '@/interfaces/IComments';
import { preProcessFile } from 'typescript';

const props = defineProps<IComment>();
const emits = defineEmits(['SayVue', 'ByeVue']);
const clicked = () => {
    emits('SayVue', props.id);
}
const actPro = () => {
    emits('ByeVue', props.title)
}
</script>
<style scoped>
</style>    