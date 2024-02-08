<script >
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

export default {
    name: 'BoolFlix',
    components: { AppHeader, AppMain },
}

</script>

<template>
    <AppHeader />
    <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.sass'
</style>

