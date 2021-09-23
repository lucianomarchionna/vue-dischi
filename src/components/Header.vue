<template>
  <header>
    <img alt="Spotify logo" src="../assets/img/logo-spotify.png">
  </header>
</template>

<script>
export default {
  name: 'Header',
  props: {
    
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
@import "../style/generals";

  header{
    width: 100%;
    height: 10vh;
    display: flex;
    background-color: $primary-color;
    img{
      margin-left: 20px;
      justify-content: start;
    }
  }
</style>
