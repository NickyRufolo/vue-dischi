<template>
  <div id="app">
    <HeaderComp @emitGenere="funzioneGenSelected" :propsGeneri="ArrayGeneri"/>
    <MainComp @emitGeneri="methodsListaGeneri" :propsSelectedGen="SelectGeneri"/>
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
  },
  data(){
    return {
      ArrayGeneri: [],
      SelectGeneri: ""
    }
  },
  methods: {
    methodsListaGeneri(valueEmitGeneri){   //richiamo la funzione nell'emit per associare valore dell'array in Appvue
      this.ArrayGeneri = valueEmitGeneri
    },
    funzioneGenSelected(valueGenselected){
      this.SelectGeneri = valueGenselected
    }
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

<!-- Ciao ragazzi,
Esercizio di oggi: Vue Dischi
nome repo: vue-dischi

Descrizione:
Continuate a lavorare nella stessa repo di ieri e aggiungete una select per filtrare i dischi in base al genere: quando l'utente seleziona un genere dalla lista, vengono visualizzati solamente i dischi con il genere corrispondente.

Bonus:
Aggiungere un ulteriore select che filtra gli album per artista. -->