<script >
import AppSerchbar from './AppSearchbar.vue';
export default {
    name: 'AppHeder',
    components: {
        AppSerchbar
    },
}

</script>

<template>
    <div class="container d-flex">
        <h1>BoolFlix</h1>
        <AppSerchbar />
    </div>
</template>

<style lang="scss" scoped></style>