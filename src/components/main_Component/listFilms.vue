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
    <section id="films-list">
        <h1>Films</h1>
        <ProductionCard v-for="movie in store.movies" :key="movie.id" :production="movie" />
    </section>
</template>

<style scoped></style>