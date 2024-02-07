<script >
import axios from 'axios';
import { store } from './data/store.js';
import AppMain from './components/AppMain.vue';
import AppHeader from './components/AppHeader.vue'

export default {
    name: 'BoolFlix',
    components: {
        AppHeader,
        AppMain
    },
    methods: {
        serchedResults(serchFilm) {
            const endpointFilm = `https://api.themoviedb.org/3/search/movie?query=${serchFilm}&api_key=c3bd16a79a46d1ae2f5c9428ff80fe05`
            axios.get(endpointFilm).then(res => {
                store.films = res.data.results
            })
        }
    }
}
</script>

<template>
    <AppHeader />
    <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.sass'
</style>

