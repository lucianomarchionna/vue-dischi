<template>
  <div class="main-dimension">
        <div class="container-album">
            <div class="album" v-for="(album, index) in albumsList" :key="index">
                <Album :item="album"/>
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
        Album
    },
    data(){
        return{
            APIUrl: "https://flynn.boolean.careers/exercises/api/array/music",
            albumsList: []
        }
    },
    created(){
        this.getAlbums();
    },
    methods: {
        getAlbums(){
            axios.get(this.APIUrl)
            .then(res =>{
                console.log(res);
                this.albumsList = res.data.response;
            })
        }
    }
}
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