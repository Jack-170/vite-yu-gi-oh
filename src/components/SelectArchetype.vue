<script>

import { store } from '../store';

export default{
    name:'SelectArchetype',


    data(){
    return{
      store,
      opzioneSelezionata: ''
     }
    },

    

}

</script>

<template>


   <div class="container">

   
    <select class="form-select mb-4 w-25" v-model="opzioneSelezionata">
      <option value="" disabled>

        Select archetype
      
      </option>

      <option v-for="type in store.archetypeNames" :key="type.id" value="">
        {{ type.archetype_name }}
      </option>

      


  
    


      
    </select>
    <p v-if="opzioneSelezionata">Hai selezionato: {{ opzioneSelezionata }}</p>
 

   </div>
   

 
</template>

<style lang="scss" scoped>

@use '../styles/general.scss' as *;
@use '../styles/partials/mixins' as *;











</style>
