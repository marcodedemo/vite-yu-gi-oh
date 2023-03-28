<script>

import {store} from './store';
import axios from 'axios';

import AppCards from './components/AppCards.vue';

  export default{

    data() {
      return {

        store,


      }
    },

    components:{
      AppCards,
    },
    
    created(){
      axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0").then((res)=>{

        console.log(res.data.data);

        this.store.cards = res.data.data

      });
    }


  }


</script>



<template>
  <div>

    <h1>Yu Gi Oh Cards</h1>

    <div id="loading" v-if="store.cards.length < 50">
      Loading...
    </div>

    <AppCards v-else></AppCards>
    
  </div>
</template>




<style lang="scss" scoped>

h1{
  text-align: center;
  padding-top: 50px;
}

#loading{
  text-align: center;
}

</style>
