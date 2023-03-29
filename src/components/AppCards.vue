<script>

    import axios from 'axios';
import {store} from '../store';

    import CardItem from './CardItem.vue';
    import CardSearch from './CardSearch.vue';


  export default{

    data(){
      return{

        store,
        
      }
    },

    components:{
        CardItem,
        CardSearch,

    },

    methods: {
        
        search(){

            this.store.APIsearchedInfo = "&fname=" + this.store.cardName;

            axios.get(`${this.store.APIcall}${this.store.APIsearchedInfo}`).then((res)=>{
                
                this.store.cards = res.data.data;
                
            })
        }
    },
  }


</script>

<template>

    <CardSearch @charaterSearch="search()"></CardSearch>

  <div id="card-container">

    <CardItem v-for="card in store.cards" :card-name="card.name" :image="card.card_images[0].image_url" :card-type="card.type"></CardItem>

  </div>

</template>

<style lang="scss" scoped>

#card-container{
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 20px;

    padding: 50px;
}

</style>
