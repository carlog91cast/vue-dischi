

<template>
    <div class="container song-container">
        <div class="row">
            <div v-for(song, index) in   class="col-2">
                <SingleSong />
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
        return{
            url: "https://flynn.boolean.careers/exercises/api/array/music",
            songList:[],
        }
    },
    created() {
        this.getSongCard();
    },
    methods: {
        getSongCard() {
            axios.get('https://flynn.boolean.careers/exercises/api/array/music')
            .then((result) =>{
                console.log(result.data.result)
                this.songs = result.data.result;
            })
            .catch((error)=>{
                console.warn(error);
            })
        }
    }
}

</script>

<style lang="scss" scoped>
@import '../style/common.scss';

.song-container{
    background-color: #1E2D3B;
    height: 100%;
}
</style>
