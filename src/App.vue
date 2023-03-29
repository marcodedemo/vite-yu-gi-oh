<script>

import {store} from './store';
import axios from 'axios';

import AppCards from './components/AppCards.vue';
import AppLoader from './components/AppLoader.vue';


  export default{

    data() {
      return {

        store,


      }
    },

    components:{
      AppCards,
      AppLoader,
    },
    
    created(){


      axios.get(this.store.APIcall).then((res)=>{

        this.store.cards = res.data.data;

        this.store.generatedCardNumber = this.store.cards.length;

      });
    }


  }


</script>



<template>
  <div>

    <h1>Yu Gi Oh Cards</h1>

    <AppLoader v-if="!store.cards.length > 0"></AppLoader>
    <AppCards v-else></AppCards>
    
  </div>
</template>




<style lang="scss" scoped>

h1{
  text-align: center;
  padding-top: 50px;
}



</style>
