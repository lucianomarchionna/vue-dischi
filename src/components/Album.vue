<template>
  <div class="album">
    <img :src="item.poster" :alt="item.title">
    <div class="subtitles">
      <h3 id="title">{{item.title.toUpperCase()}}</h3>
      <h5 id="author">{{item.author}}</h5>
      <h5 id="year">{{item.year}}</h5>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Album',
    props: ['item']
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