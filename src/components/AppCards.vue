<script>

    import axios from 'axios';
    import {store} from '../store';

    import CardItem from './CardItem.vue';
    import CardSearch from './CardSearch.vue';
    import GeneratedCards from './GeneratedCards.vue';


  export default{

    data(){
      return{

        store,
        
      }
    },

    components:{
        CardItem,
        CardSearch,
        GeneratedCards,

    },

    methods: {
        
        search(){

            // se la ricerca ha entrambi i parametri
            if (this.store.cardName != "" && this.store.cardRank != "") {
                
                // inserisco entrambi i parametri nella ricerca
                this.store.APIsearchedInfo = "&fname=" + this.store.cardName + "&level=" + this.store.cardRank;

            // altrimenti se la ricerca comprende solo il nome
            } else if(this.store.cardName != "" && this.store.cardRank == ""){

                // filtro solo tramite il nome
                this.store.APIsearchedInfo = "&fname=" + this.store.cardName;

            // altrimenti se la ricerca comprende solo il rank
            }else if(this.store.cardName == "" && this.store.cardRank != ""){

                // filtro solo tramite il rank
                this.store.APIsearchedInfo = "&level=" + this.store.cardRank;

            }else{
                
                // se entrambi sono vuoti lascio la richiesta API standard
                this.store.APIsearchedInfo = "";
            }

            

            axios.get(`${this.store.APIcall}${this.store.APIsearchedInfo}`).then((res)=>{
                
                this.store.cards = res.data.data;

                this.store.generatedCardNumber = this.store.cards.length;
                
            })
        }
    },
  }


</script>

<template>

    <CardSearch @charaterSearch="search()"></CardSearch>

    <GeneratedCards></GeneratedCards>


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
