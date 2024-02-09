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
    <header>
        <navbar class="container d-flex justify-content-between navbar">
            <h1 class="title">BOOLFLIX</h1>
            <form @submit.prevent="$emit('search-movies', inputSearch)" id="searchBar">
                <input class="searchbar" type="text" :placeholder="placeholder" v-model.trim="inputSearch">
                <button>{{ buttonLabel }}</button>
            </form>
        </navbar>

    </header>
</template>

<style lang="scss" scoped>
header {
    // Posizione fissa header
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    padding: 10px;
    z-index: 1;


    display: flex;
    align-items: center;
    background: linear-gradient(to bottom, #070707 5px, #070707cc);
    height: 5rem;
    align-items: center;
    box-shadow: 0px 20px 20px 20px rgb(10 10 10) inset, 9px 0 0px rgb(255 255 255 / 50%);
}

.navbar {
    align-items: center;
    font-size: 15px;
    padding-left: 4%;
    padding-right: 4%;
}

.title {
    color: rgb(229, 9, 20);
    fill: currentColor;
    display: block;
}

.searchbar {
    padding: 4px 8px;
    color: #fff;
    background: #0f0f0f;
    border-radius: 2px;
    background-color: #0f0f0f;
    width: 15rem;
    border: 1px solid #595959;
    margin: 0.3rem;
}
</style>
