<script>
import { store } from '../../data/store.js';
import FilmCard from './FilmCard.vue';
export default {
    name: 'ListFilms',
    data: () => ({
        store
    }),
    components: {
        FilmCard
    }
}
</script>

<template>
    <FilmCard v-for="film in store.films" :key="film.id" :FilmCard="film" />
</template>

<style scoped></style>