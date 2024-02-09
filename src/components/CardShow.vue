<script>
export default {
    name: 'CardShow',
    props: {
        show: Object,
        maxVote: Number,
    },
    computed: {
        // Creo delle computed per i titoli e scrivere più veloce la lingua
        title() {
            return this.show.title || this.show.name;
        },
        originalTitle() {
            return this.show.original_title || this.show.original_name;
        },
        lang() {
            return this.show.original_language;
        },

        // controllo se c'è l'immagine che mi interessa, mi devo scrivere quali immagini io abbia
        isImage() {
            const flags = ['en', 'it'];
            return flags.includes(this.lang);
        },
        flagImg() {
            return new URL(`../assets/img/${this.lang}.png`, import.meta.url).href;
        },

        showImg() {
            return `https://image.tmdb.org/t/p/w342${this.show.poster_path}`
        },
        showVote() {
            return Math.floor(parseInt(this.show.vote_average) / 2);
        },
    },
}
</script>

<template>
    <div class="card-container">
        <div class="poster-container">
            <img v-if="show.poster_path" class="poster" :src="showImg" :alt="title">
            <div v-else class="noflag">NO IMG</div>
            <div class="info-overlay">
                <ul class="show-info">
                    <li><strong>Titolo: </strong>{{ title }}</li>
                    <li><strong>Titolo originale: </strong>{{ originalTitle }}</li>
                    <li>
                        <img v-if="isImage" class="w-25" :src="flagImg" :alt="lang">
                        <div v-else class="noflag">{{ lang }}</div>
                    </li>
                    <li>
                        <div class="d-flex gap-2">
                            Voto:
                            <div v-for="i in maxVote" :key="i">
                                <i v-if="i <= showVote" class="fas fa-star"></i>
                                <i v-else class="far fa-star"></i>
                            </div>
                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.poster {
    height: 18rem;
}

.card-container {
    position: relative;
    width: 15rem;
    /* Imposta la larghezza della card */
    overflow: hidden;
}

.poster-container {
    position: relative;
}

.poster {
    width: 100%;
    transition: filter 0.3s ease-in-out;
}

.info-overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: rgba(0, 0, 0, 0.7);
    /* Sfondo scuro per overlay */
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    opacity: 0;
    transition: opacity 0.3s ease-in-out;
}

.card-container:hover .info-overlay {
    opacity: 1;
}

.show-info {
    list-style: none;
    padding: 0;
    margin: 0;
    color: #fff;
    text-align: center;
}

.show-info li {
    margin-bottom: 10px;
}
</style>