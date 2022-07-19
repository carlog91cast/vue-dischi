<template>
    <div class="song-card">
        <div class="song-img">
            <img :src="songCard.poster" alt="">
        </div>

        <h3>{{ songCard.title }}</h3>
        <h4>{{ songCard.author }}</h4>
        <h5>{{ songCard.year }}</h5>
    </div>
</template>

<script>
export default {
    name: "SingleSong",
    props: ['songCard'],
}
</script>

<style lang="scss" scoped>
@import'@/style/common.scss';
@import "~bootstrap/scss/bootstrap";
.song-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    background-color: #2E3A46 ;
    text-align: center;
    margin-bottom: 1rem;

    .song-img {
        width: 100%;
        aspect-ratio: 1/1;
        background-color: black;
    }

    img {
        width: 100%;
    }

    h3 {
        width: 100%;
        font-size: 20px;
        padding: 0.5rem 0;
        margin-bottom: 0;
        color: white;
    }

    h4 {
        width: 100%;
        font-size: 1.2rem;
        color:  darkgray;
        margin-top: 20px;
    }

    h5 {
        width: 100%;
        font-size: 1rem;
        color:   darkgray;
    }
}
</style>