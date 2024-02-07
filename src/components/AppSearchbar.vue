<script>
export default {
    name: 'AppSerchbar',
    data: () => ({
        serchFilm: ''
    }),
    emits: ['serch-film'],
}
</script>

<template>
    <div class="input-group mb-3">
        <input @keyup.enter="$emit('serch-film', serchFilm)" type="text" class="form-control"
            placeholder="Cerca il tuo film" v-model.trim="serchFilm">
        <button class="btn btn-outline-secondary" type="button" @click="$emit('serch-film', serchFilm)">Button</button>
    </div>
</template>

<style></style>