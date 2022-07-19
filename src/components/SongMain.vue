

<template>
    <div class="container">
        <ListSong />
        <div class="row">
            <div class="col-2">
                <SingleSong />
            </div>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import SingleSong from './SingleSong.vue';
import ListSong from './ListSong.vue';

export default {
    name: "SongMain",
    components: {
        SingleSong,
        ListSong,
    },
    data() {

    },
    created() {
        this.getSongCard;
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
</style>
