<script>
import CardShow from './CardShow.vue'
export default {
    name: 'SectionMain',
    components: { CardShow },
    props: {
        shows: Object,
        title: String
    },
    methods: {
        scroll(direction) {
            const carousel = this.$refs.carousel;

            if (carousel) {
                const scrollAmount = 300; // Adjust this value according to your needs
                if (direction === -1) {
                    carousel.scrollLeft -= scrollAmount;
                } else if (direction === 1) {
                    carousel.scrollLeft += scrollAmount;
                }
            }
        }
    }
}
</script>

<template>
    <h4 class="mt-5" v-if="shows.length">{{ title }}</h4>
    <div class="netflix-carousel" ref="carousel">
        <div class="col" v-for="show in shows" :key="show.id">
            <CardShow :show="show" :maxVote="5" />
        </div>
    </div>
</template>

<style lang="scss" scoped>
.netflix-carousel {
    display: flex;
    overflow-y: hidden;
    overflow-x: hidden;
    // scroll-snap-type: x mandatory;
    padding: 20px 0;
    gap: 2rem;
    height: 20rem;
    align-items: center;
    scroll-behavior: smooth;
}

h4 {
    color: darkgray;
}
</style>