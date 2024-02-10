<template>
    <div>
        <button @click="clicked($event)">Click me!</button>
        <button @click="actPro($event)">Soy una actividad pro</button>
        <ul>
            <CommentItem @bye-vue="actPro" @say-vue="clicked($event)" v-bind="comments" v-for="(comments, index) in CommentsData" :key="index" />
        </ul>
    </div>
</template>

<script setup lang="ts">
    import CommentsData from '@/data/CommentsData'
    import CommentItem from './CommentItem.vue';

    const clicked = (event: any) => {
        alert('Selccionaste: ' + event);
    }
    const actPro = (event: any) => {
        alert('Soy la actividad Pro ')
    }
</script>

<style scoped></style>