<script>
export default {
    name: 'FilmCard',
    props: {
        titolo: String,
        titoloOriginale: String,
        lingua: String,
        voto: Number
    }
}
</script>

<template>
    <div>
        <h1>{{ titolo }}</h1>
        <h2>{{ titoloOriginale }}</h2>
        <span>{{ lingua }}</span>
        <span>{{ voto }}</span>
    </div>
</template>

<style lang="scss" scoped></style>