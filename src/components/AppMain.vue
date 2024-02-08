<script >
import ListFilms from './main_Component/listFilms.vue';
export default {

    name: 'AppMain',
    components: {
        ListFilms
    }
}

</script>

<template>
    <main>
        <div class="container">
            <ListFilms />
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: grey;
    border: 1px solid;
    height: 500px;
}
</style>