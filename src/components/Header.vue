<template>
  <header>
    <div class="elements">
      <img alt="Spotify logo" src="../assets/img/logo-spotify.png">
      <select class="font-size" name="genre" id="genre">
        <option value="">Tutti</option>
      </select>
    </div>
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
    background-color: $primary-color;

    .elements{
      display: flex;
      justify-content: space-between;
      align-items: center;
      width: 100%;
      height: 100%;
      img{
        margin-left: 20px;
        height: 100%;
        
      }

      .font-size{
        margin-right: 50px;
        height: 30px;
        padding: 0 20px;
      }

    }
    
  }
</style>
