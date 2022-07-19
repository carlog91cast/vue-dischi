

<template>
    <main>
        <div class="main-wrapper">
            <div class="container-fluid">
                <div class="row row-cols-md-5 row-cols-sm-3  ">
                    <div v-for="(song, index) in songList" class="col" :key="index" songCard="song">
                        <SingleSong :songCard="song" />
                    </div>
                </div>
            </div>
        </div>
    </main>
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
@import "~bootstrap/scss/bootstrap";

main{
    background-color: #1E2D3B;;
    height: 100%;
    
    .main-wrapper{
        padding: 50px 0;
        margin: 0 auto;
        width: 70%;
        .col{
            display: flex;
        }
    }
}
</style>
