<script>


export default {
    name: 'FilmCard',
    props: {
        production: Object
    },
    computed: {
        title() {
            return this.production.title || this.production.name
        },
        originalTitle() {
            return this.production.original_title || this.production.original_name
        },
        hasFlag() {
            const flag = ['it', 'en'];
            return flag.includes(this.production.original_language);
        },
        flagSrc() {
            const url = new URL(`../assets/img/${this.production.original_language}.png`, import.meta.url);
            return url.href;
        }
    }
}
</script>

<template>
    <img :src="image" :alt="production.poster_path">
    <ul>
        <li> {{ title }}</li>
        <li>{{ originalTitle }}</li>
        <li>
            <img v-if="hasFlag" :src="flagSrc" :alt="production.original_language">
            <span v-else>{{ production.original_language }}</span>
        </li>
        <li>{{ production.vote_average }}</li>
    </ul>
</template>

<style lang="scss" scoped></style> 