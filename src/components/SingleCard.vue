<script>

export default{
    name:'SingleCard',

    props:{
        info:Object
    },


}

</script>

<template>


    <div v-for="image in info.card_images" :key="image.id">
        <img class="img-fluid mb-3" :src="image.image_url" alt="">
        <span>{{ info.name }}</span>
        <div>{{info.archetype}}</div>
    </div>
    

    

 
</template>

<style lang="scss" scoped>

@use '../styles/general.scss' as *;
@use '../styles/partials/mixins' as *;


.box-img{
    height: 150px;
    width: 100%;
    border: 1px solid black;
}






</style>
