<template>
<header>
<div class="spotify-logo">
  <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/1/19/Spotify_logo_without_text.svg/2048px-Spotify_logo_without_text.svg.png" alt="">
</div>
        <!-- select -->
<div class="w-auto me-3">
  <select class="form-select" v-model="genereSelected"
    @change="$emit(`emitGenere`, genereSelected)"
    aria-label="Default select example">
    <option disabled value="">Filtra per Genere</option>
<option :value="elem" v-for="(elem, index) in propsGeneri" :key="index">{{elem}}
</option>
</select>
</div>
</header>
</template>

<script>
export default {
  name: 'HeaderComp',
  props: {
    propsGeneri : Array
  },
  data(){
    return {
      genereSelected: ""
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
header {
  background-color:#2E3A46;
  height: 100px;
  display: flex;
  align-items: center;
  padding-left: 10px;
}
.spotify-logo > img {
  height: 50px;
  width: 50px;
}
</style>
