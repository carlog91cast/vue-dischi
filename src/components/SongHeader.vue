

<template>
    <header>
        <section>
            <div class="spotify-logo">
                <img class="w-100" src="../assets/Spotify_logo_without_text.svg.png" alt="spotify logo">
            </div>
            <!-- <div>inserisco il component in cui vado ad inserire il select</div> -->
        </section>

    </header>
</template>

<script>
export default {
}
</script>

<style lang="scss" scoped>
@import '../style/common.scss';

header {
    width: 100vw;
    height: 20%;
    background-color: #2E3A46;
    color: white;

    .spotify-logo {
        img {
            height: 30px;
            padding: 0 1.5rem;
            margin-top: 10px;
        }
    }

}
</style>