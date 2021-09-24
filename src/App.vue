<template>
  <div id="app">  
    <Header :genres="genresList" @changedGenre="startSearch" />
    <Main :selectedGenre="genreToSearch" @genresReady="getGenresList"/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main
  },
  data(){
    return{
      genresList: [],
      genreToSearch: "",
    }
  },
  methods:{
    getGenresList(allGenres){
      this.genresList = allGenres;
    },
    startSearch(genreToSearch){
      this.genreToSearch = genreToSearch;
    },
  },
};

</script>

<style lang="scss">
@import "style/generals";
</style>
