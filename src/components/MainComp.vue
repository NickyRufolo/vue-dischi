<template>
    <main>
        <div class="divTutteCard">
            <DischiComp v-for=" (elem,index) in functionComputed" :key="index" :propsDischi="elem"/>
        </div>

    </main>
</template>
    
<script>
import DischiComp from './DischiComp'
import axios from 'axios'


export default {
    name: 'MainComp',
    props: {
    propsSelectedGen : String
    },
    components: {
    DischiComp
},

data() {
    return {
    dataDischi: ``,
    ArrayGeneri: []
    }
},
//Con la Funzione Computed posso attivare il filter al cambiamento della variabile propsSelectedGen
computed:{
    functionComputed(){
        //condizone per generare gli album
        if (this.propsSelectedGen == ``){
            return this.dataDischi
        }
        else{
            return this.dataDischi.filter((elem)=>{
                return elem.genre == this.propsSelectedGen
            })
        }
    }
},
    mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
        this.dataDischi = response.data.response 
        //  this.dataDischi recupero info dentro data
        // response.data.response recuperiamo l'array di tutti i 10 dischi presenti nel reponse nella chiamata GET dell'api
        this.dataDischi.forEach(elem => {
            if(!this.ArrayGeneri.includes(elem.genre)){ //se il genere non è presente nell'array
                this.ArrayGeneri.push(elem.genre)
            }
        this.$emit(`emitGeneri`, this.ArrayGeneri) //invoco la funzione emit per spostare i dati dell'array in app vue
        });
    })
}
}

</script>
    
    <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
main {
    background-color: #1E2D3B;
    height: 700px;
    width: 100%;

}
.divTutteCard {
display: flex;
width: 80%;
margin:auto;
padding: 10px 10px;
justify-content: center;
flex-wrap: wrap;
}

</style>
    