<script>

import SingleCard from './SingleCard.vue';

import { store } from '../store';

export default{
    name:'CardList',

    components:{
        SingleCard,
    },

    data(){
    return{
      store,
    }
  },


}

</script>

<template>

 

    <div class="container">

        <div class="ms-container">

            <div class="row">

                <div v-for="card in store.cardList" :key="card.id" class="ms-col">
                    <SingleCard :info="card"/>
                </div>
                


            </div>


        </div>


    </div>

  
</template>

<style lang="scss" scoped>

@use '../styles/general.scss' as *;
@use '../styles/partials/mixins' as *;

    


.container{
    background-color: white;
    @include center;

    .ms-container{
        width: 90%;
        height: 95%;
    }
}


.row{
    @include wrap;
    .ms-col{
        width: calc((100% * 1/5) - 20px);
        margin: 0 10px 10px;
        background-color: #d48f38;
        padding: 0;
    }
}



</style>
