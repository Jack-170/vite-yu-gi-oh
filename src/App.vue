<script>

import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';
import axios from 'axios';
import SelectArchetype from './components/SelectArchetype.vue'


import { store } from './store';

export default{
  components:{
    AppHeader,
    CardList,
    SelectArchetype
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
    },

    getArcheotype(){
      axios
      .get(store.apiArchetypeUrl)
      .then((response => {

        console.log(response.data)

        store.archetypeNames = response.data

      }))
      .catch((err)=>{
        console.log("Errori", err)
      })

    }
  },

  created(){

    this.getCard()

    this.getArcheotype()


  }
}



</script>

<template>
  <AppHeader message="YU-GI-OH API"/>


  <main>

    <SelectArchetype/>

    <CardList/>

  </main>





 
  
</template>

<style lang="scss">
@use './styles/general.scss' as *;


</style>
