<script>

    import {store} from '../store';

  export default{

    data(){
      return{

        store,
        
      }
    },

  }


</script>

<template>
  <div id="search">
    
    <input type="text" placeholder="Cerca la carta" v-model="this.store.cardName" @keyup.enter="$emit('charaterSearch')">

    <button @click="$emit('charaterSearch')">Cerca</button>


  </div>
</template>

<style lang="scss" scoped>

    #search{
        display: flex;
        justify-content: center;
        gap: 10px;

        padding: 20px;
    }



</style>
