<template>
  <div class="main-dimension">
        <div class="container">
            <div class="single">
                <div v-for="(album, index) in albumsList" :key="index">
                    <Album :item="album" />
                </div>
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
    height: 90vh;
    background: $secondary-color;
}
</style>