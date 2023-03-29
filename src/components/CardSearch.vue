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

    <select name="level" id="level" v-model="this.store.cardRank">
        <option value=""></option>
        <option value="1">Rank 1 </option>
        <option value="2">Rank 2 </option>
        <option value="3">Rank 3 </option>
        <option value="4">Rank 4 </option>
        <option value="5">Rank 5 </option>
        <option value="6">Rank 6 </option>
        <option value="7">Rank 7 </option>
        <option value="8">Rank 8 </option>
        <option value="9">Rank 9 </option>
        <option value="10">Rank 10 </option>
        <option value="11">Rank 11 </option>
        <option value="12">Rank 12 </option>
        <option value="13">Rank 13 </option>


    </select>

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
