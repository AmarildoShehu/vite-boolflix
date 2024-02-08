<script >
import axios from 'axios';
import { store } from './data/store.js';
import AppMain from './components/AppMain.vue';
import AppHeader from '../src/components/AppHeader.vue'

export default {
    name: 'Boolflix',
    components: {
        AppHeader,
        AppMain
    },
    methods: {
        serchedResults(serchMovies) {
            const endpointMovies = `https://api.themoviedb.org/3/search/movie?query=${serchMovies}&api_key=c3bd16a79a46d1ae2f5c9428ff80fe05`
            axios.get(endpointMovies).then(res => {
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

