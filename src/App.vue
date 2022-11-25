<template>
  <div id="app">
    <HeaderComp/>
    <MainComp/>
  </div>
</template>

<!-- Descrizione:
Create un nuovo progetto utilizzando Vue CLI e definite i componenti necessari per strutturare il layout come da screenshot allegato.
Al caricamento della pagina, effettuate una chiama ajax all'API di boolean:
https://flynn.boolean.careers/exercises/api/array/music
e con i dati restituiti, stampate una card per ogni disco musicale.
Bonus:
Creare un componente loader da visualizzare fintantoché i risultati non sono pronti. -->

<script>
import HeaderComp from './components/HeaderComp.vue'
import MainComp from './components/MainComp.vue'

export default {
  name: 'App',
  components: {
    HeaderComp,
    MainComp
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
