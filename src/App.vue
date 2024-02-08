<script >
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

import { store } from './data/store.js'
const endpoint = 'https://api.themoviedb.org/3/search';
const apiKey = '&api_key=c3bd16a79a46d1ae2f5c9428ff80fe'

export default {
    name: 'BoolFlix',
    components: { AppHeader, AppMain },
    data: () => ({
        store
    }),
    methods: {
        fetchShows(input) {
            if (!input) return;
            const urlMovies = endpoint + `/movie?query=${input}` + apiKey;
            const urlTvShows = endpoint + `/tv?query=${input}` + apiKey;
            axios.get(urlMovies).then(res => {
                store.listMovies = res.data.results
            });
            axios.get(urlTvShows).then(res => {
                store.listTvShows = res.data.results
            });
        }
    },
}

</script>

<template>
    <AppHeader @search-movies="fetchShows" buttonLabel="Cerca" placeholder="Scrivi qui" />
    <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.sass'
</style>

