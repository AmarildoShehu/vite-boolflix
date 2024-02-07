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
    <div v-for="film in store.films" :key="film.result.id">
        <FilmCard :titolo="film.results.title" :titoloOriginale="film.results.original_title"
            :lingua="film.results.original_language" :voto="film.results.vote_average" />
    </div>
</template>

<style scoped></style>