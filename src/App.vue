<script>

import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import axios from 'axios';

import { store } from './store';

export default{
  components:{
    AppHeader,
    CardList,
  },
  
  data(){
    return{
      store,
    }
  },

  methods:{
    getCard(){
      axios
      .get(store.apiUrl)
      .then((res => {

        console.log(res.data.data)
        
        store.cardList = res.data.data;
        // console.log(store.cardList)

      }))
      .catch((err)=>{
        console.log("Errori", err)
      })
    }
  },

  created(){

    this.getCard()

  }
}



</script>

<template>
  <AppHeader message="YU-GI-OH API"/>

  <CardList/>



 
  
</template>

<style lang="scss">
@use './styles/general.scss' as *;


</style>
