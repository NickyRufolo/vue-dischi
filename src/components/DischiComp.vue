<template>
    <div class="divCard">
            <img :src="propsDischi.poster" alt="">
            <br><br>
            <h4>{{propsDischi.title}}</h4>
            <h6>{{propsDischi.author}}</h6>
            <h6>{{propsDischi.genre}}</h6>
            <h6>{{propsDischi.year}}</h6>
    </div>
</template>
    
<script>
export default {
    name: 'DischiComp',
    props: {
        propsDischi : Object
    }
}
</script>
    
    <!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.divCard > img {
width: 130px;

}
.divCard {
background-color: #2E3A46;
height: 300px;
color: white;
padding: 10px 10px;
margin: 15px 15px;
width: calc((100% / 5 ) - 30px);}
h4 {
    font-size: 1.3rem
}
h6 {
    font-size: 1rem

}
</style>
    