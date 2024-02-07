<script >
import AppSearchbar from '../components/AppSearchbar.vue';
export default {
    name: 'AppHeder',
    components: {
        AppSearchbar
    },
}

</script>

<template>
    <div class="container d-flex">
        <h1>BoolFlix</h1>
        <AppSearchbar />
    </div>
</template>

<style lang="scss" scoped></style>