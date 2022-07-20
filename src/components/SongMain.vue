

<template>
    <main>
        <div class="main-wrapper">
            <div class="form-floating mb-3">
                <select class="form-select" id="floatingSelect" aria-label="Floating label select example">
                    <option selected>Filtra per genere</option>
                    <option value="1">Rock</option>
                    <option value="2">Pop</option>
                    <option value="3">Jazz</option>
                    <option value="4">Metal</option>
                </select>
            </div>
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
            genresList: [],
            filter: "",
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
        },
        filterGenres() {
            const genresList = [];
            this.songList.forEach((album) => {
                if (!genresList.includes(album.genre)) {
                    genresList.push(album.genre);
                    this.genresList.push(album.genre);
                    console.log(genresList);
                }
            });
            return genresList;
            
        },
    },

created() {
    this.getSongCard();
},
}

</script>

<style lang="scss" scoped>
@import '../style/common.scss';
@import "~bootstrap/scss/bootstrap";

main {
    background-color: #1E2D3B;
    ;
    height: 100%;
    width: 100vw;

    .main-wrapper {
        padding: 50px 0;
        margin: 0 auto;
        width: 70%;

        .col {
            display: flex;
        }
    }
}
</style>
