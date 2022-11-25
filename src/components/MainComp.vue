<template>
    <main>
        <div class="divTutteCard">
            <DischiComp v-for=" (elem,index) in dataDischi" :key="index" :propsDischi="elem"/>
        </div>
    </main>
</template>
    
<script>
import DischiComp from './DischiComp'
import axios from 'axios'


export default {
    name: 'MainComp',
    components: {
    DischiComp
},
data() {
    return {
    dataDischi: ``
    }
},
mounted() {
    axios.get('https://flynn.boolean.careers/exercises/api/array/music')
    .then((response) => {
        this.dataDischi = response.data.response 
        //  this.Dischi recupero info dentro data
        // response.data.response recuperiamo l'array di tutti i 10 dischi presenti nel reponse sella chiamata GET dell'api
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
    