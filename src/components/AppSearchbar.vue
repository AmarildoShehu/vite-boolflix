<script>
export default {
    name: 'AppSerchbar',
    data: () => ({
        searchFilm: ''
    }),
    props: {
        buttonLabel: String,
        placeholder: String
    },

    emits: ['search-film', 'term-change'],

}
</script>

<template>
    <form @submit.prevent="$emit('search-film',)">
        <input type="text" v-model.trim="searchFilm" @keyup="$emit('term-change', searchFilm)" :placeholder="placeholder">

        <button>{{ buttonLabel }}</button>
    </form>
    <!-- <div class="align-self-center">
        <input @keyup.enter="$emit('serch-film', serchFilm)" type="text" placeholder="film" v-model.trim="serchFilm">
        <button type="button" @click="$emit('serch-film', serchFilm)">Button</button>
    </div> -->
</template>

<style scoped></style>