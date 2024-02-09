<script >

import SectionMain from './SectionMain.vue';
export default {
    name: 'Appmain',
    components: { SectionMain },
    props: {
        shows: Object
    },
    methods: {
        scrollShows(type, direction) {
            const sectionRef = type === 'movies' ? this.$refs.moviesSection : this.$refs.tvShowsSection;

            if (sectionRef && sectionRef.scroll) {
                sectionRef.scroll(direction);
            }
        }
    }
}

</script>

<template>
    <main>
        <div class="">
            <div class=" d-flex align-items-center ">
                <span class="arrowstyle fa-solid fa-chevron-left fa-2xl" @click=" scrollShows('movies', -1)"></span>
                <div class="container">
                    <SectionMain :shows="shows.listMovies" title="Film" ref="moviesSection" />
                </div>

                <span class="arrowstyle fa-solid fa-chevron-right fa-2xl" @click="scrollShows('movies', 1)"></span>
            </div>
            <div class="d-flex align-items-center">
                <span class="arrowstyle fa-solid fa-chevron-left fa-2xl" @click="scrollShows('tvShows', -1)"></span>
                <div class="container">
                    <SectionMain :shows="shows.listTvShows" title="Programmi TV" ref="tvShowsSection" />
                </div>
                <span @click="scrollShows('tvShows', 1)" class="arrowstyle fa-solid fa-chevron-right fa-2xl"></span>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background: #070707ef;
    padding-top: 5rem;
}

.arrowstyle {
    margin: 0 2rem 0 2rem;
    color: white
}
</style>
