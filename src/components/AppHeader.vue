<script >
export default {
    name: 'AppHeader',
    data: () => ({
        inputSearch: '',
    }), props: {
        buttonLabel: String,
        placeholder: String
    },
    emits: ['search-movies']
}
</script>

<template>
    <header class="container d-flex justify-content-between">
        <h1>Boolflix</h1>
        <form @submit.prevent="$emit('search-movies', inputSearch)" id="searchBar">
            <input type="text" :placeholder="placeholder" v-model.trim="inputSearch">
            <button>{{ buttonLabel }}</button>
        </form>
    </header>
</template>

<style lang="scss" scoped>
header {
    height: 100px;
    border: 1px solid black;
}
</style>
