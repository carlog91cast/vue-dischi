

<template>
    <div class="container song-container">
        <div class="row">
            <div class="col-2">
                <SingleSong v-for="(song, index) in songList" :key="index" :songCard="song" />
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import SingleSong from './SingleSong.vue';


export default {
    name: "SongMain",
    components: {
        SingleSong,
    },
    data() {
        return {
            songList: [],
        }
    },
    methods: {
        getSongCard() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
                .then((result) => {
                    console.log(result.data.response)
                    this.songList = result.data.response;
                })
                .catch((error) => {
                    console.warn(error);
                })
        }
    },
    created() {
        this.getSongCard();
    },
}

</script>

<style lang="scss" scoped>
@import '../style/common.scss';

.song-container {
    background-color: #1E2D3B;
    height: 100%;
}
</style>
