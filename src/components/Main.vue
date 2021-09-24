<template>
  <div class="main-dimension">
        <div class="container-album">
            <div class="album">
                <Album 
                    v-for="(albumItem, index) in filteredAlbums" 
                    :key="index"
                    :album="albumItem"
                />
            </div>
        </div>
  </div>
</template>

<script>
import axios from "axios"
import Album from "./Album.vue"
export default {
    name: 'Main',
    components: {
        Album,
    },
    props:{
        selectedGenre: String,
    },
    methods:{
        filteredAlbums(){
            if(this.selectedGenre === ""){
                return this.albums;
            }
            return this.albums.filter(
                (item) => item.genre === this.selectedGenre
            );
        },
    },
    data(){
        return{
            albums: [],
            genres: [],
            APIUrl: "https://flynn.boolean.careers/exercises/api/array/music",
        }
    },
    created(){
        axios.get(this.APIUrl)
        .then((res) =>{
            this.albums = res.data.response;
            this.albums.forEach((album) => {
                if (!this.genres.includes(album.genre)){
                    this.genres.push(album.genre)
                }
            });
            this.$emit("genresReady", this.genres);
        })
        .catch((err) =>{
            console.log(err);
        });
    },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/generals";

.main-dimension{
    width: 100%;
    height: calc(100vh - 10vh);
    background: $secondary-color;

    .container-album{
        width: 1170px;
        margin: auto;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        padding-top: 20px;

        .album{
            cursor: pointer;
            flex-basis: calc(100% / 5 - 24px);
            margin: 10px;
            background-color: $primary-color;
        }
    }

        
}
</style>