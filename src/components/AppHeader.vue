<script >
import axios from 'axios';
import AppSearchbar from '../components/AppSearchbar.vue';
import { store } from '../data/store.js';
import { api } from '../data';
export default {
    name: 'AppHeder',
    data: () => ({ store, }),
    components: {
        AppSearchbar
    },
    methods: {
        setTitleFilter(term) {
            store.filter = term;
        },
        searchMovie() {
            if (!store.filter) {
                store.films = []
                return;
            }
            const { baseUri, language, apikey } = api;
            const apiConfing = {
                params: {
                    query: store.filter,
                    api_key: apikey,
                    language
                }
            }
            axios.get(`${baseUri}/search/movie`, apiConfing)
                .then((res) => {
                    store.movies = res.data.results;
                })
                .catch((err) => {
                    console.error(err)
                })

        },
    },
    // emits: ['search']
}

</script>

<template>
    <div class="container d-flex">
        <h1>BoolFlix</h1>
        <AppSearchbar placeholder="scrivi il film" buttonLabel="Cerca" @search-film="searchMovie"
            @term-change="setTitleFilter" />
    </div>
</template>

<style lang="scss" scoped></style>