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
        <AppSearchbar @serch-film="$emit('serch', $event)" />
    </div>
</template>

<style lang="scss" scoped></style>