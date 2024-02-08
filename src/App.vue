<script >
import axios from 'axios';
import AppHeader from './components/AppHeader.vue'
import AppMain from './components/AppMain.vue'

import { store } from './data/store.js'

export default {
    name: 'BoolFlix',
    components: { AppHeader, AppMain },
    data: () => ({
        store
    }),
}

</script>

<template>
    <AppHeader />
    <AppMain />
</template>

<style lang="scss" scoped>
@use './assets/scss/style.sass'
</style>

