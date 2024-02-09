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
                <button class="" @click=" scrollShows('movies', -1)">Precedenti Film</button>
                <div class="container">
                    <SectionMain :shows="shows.listMovies" title="Film" ref="moviesSection" />
                </div>

                <button @click="scrollShows('movies', 1)">Successivi Film</button>
            </div>
            <div class="d-flex align-items-center">
                <button @click="scrollShows('tvShows', -1)">Precedenti Programmi TV</button>
                <SectionMain :shows="shows.listTvShows" title="Programmi TV" ref="tvShowsSection" />
                <button @click="scrollShows('tvShows', 1)">Successivi Programmi TV</button>
            </div>
        </div>
    </main>
</template>

<style lang="scss" scoped>
main {
    background: #070707ef;
    padding-top: 5rem;
}
</style>
