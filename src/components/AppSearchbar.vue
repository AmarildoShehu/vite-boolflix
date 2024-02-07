<script>
export default {
    name: 'AppSearchbar',
    data: () => ({
        searchFilm: ''
    }),
    emits: ['search-film'],
}
</script>

<template>
    <div class="input-group mb-3">
        <input @keyup.enter="$emit('search-film', searchFilm)" type="text" class="form-control"
            placeholder="Cerca il tuo film" v-model.trim="searchFilm">
        <button class="btn btn-outline-secondary" type="button" @click="$emit('search-film', searchFilm)">Button</button>
    </div>
</template>

<style></style>