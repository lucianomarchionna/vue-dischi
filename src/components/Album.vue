<template>
  <div class="album">
    <img :src="album.poster" :alt="album.title">
    <div class="subtitles">
      <h3 id="title">{{album.title.toUpperCase()}}</h3>
      <h5 id="author">{{album.author}}</h5>
      <h5 id="year">{{album.year}}</h5>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Album',
    props:[{
      album: Object,
    }]
}
</script>

<style scoped lang="scss">
@import "../style/generals";
.album{
  padding: 0 10px;

  .subtitles{
    padding: 25px;
    text-align: center;

    #title{
    color: white;
    }
    #author{
      margin-top: 10px;
    }
    h5{
      color: rgb(129, 127, 127);
    }
  }
}

</style>