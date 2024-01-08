<script>

import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue';

export default{
  components:{
    AppHeader,
    CardList,
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
