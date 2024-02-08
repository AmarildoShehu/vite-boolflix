<script>
import CardShow from './CardShow.vue'
export default {
    name: 'SectionMain',
    components: { CardShow },
    props: {
        shows: Object,
        title: String
    }
}
</script>

<template>
    <h4 class="mt-5" v-if="shows.length">{{ title }}</h4>
    <div class="netflix-carousel">
        <div class="col" v-for="show in shows" :key="show.id">
            <CardShow :show="show" :maxVote="5" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
.netflix-carousel {
    display: flex;
    overflow-x: scroll;
    scroll-snap-type: x mandatory;
    padding: 20px 0;
    gap: 2rem;
    height: 25rem;
    align-items: center
}
</style>