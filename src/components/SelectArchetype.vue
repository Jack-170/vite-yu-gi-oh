<script>

import { store } from '../store';

export default{
    name:'SelectArchetype',


    data(){
    return{
      store,
      opzioneSelezionata: '',
     }
    },
    watch: {
        opzioneSelezionata(newValue) {
          store.selectedArchetype = newValue;
        }
    }

}

    

    



</script>

<template>


   <div class="container">

   
    <select class="form-select mb-4 w-25" v-model="opzioneSelezionata" @change="$emit('changeArchetype')">

      <option value="" disabled>Scegli un archetipo</option>

      <option v-for="(type, index) in store.archetypeNames" :key="index" :value="type.archetype_name">
        {{ type.archetype_name }}
      </option>
      
    </select>

    <p v-if="opzioneSelezionata !== ''">
      Hai selezionato: {{ opzioneSelezionata }}
    </p>

    
    



   
 

   </div>
   

 
</template>

<style lang="scss" scoped>

@use '../styles/general.scss' as *;
@use '../styles/partials/mixins' as *;











</style>
