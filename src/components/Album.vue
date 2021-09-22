<template>
  <div class="album">
    <img :src="item.poster" :alt="item.title">
    <h3>{{item.title}}</h3>
    <h5>{{item.author}}</h5>
    <h5>{{item.year}}</h5>
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
// .album{
//     text-align: center;
// }
</style>