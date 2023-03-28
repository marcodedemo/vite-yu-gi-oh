<script>

    import {store} from '../store';

    import CardItem from './CardItem.vue';

  export default{

    data(){
      return{

        store,
        
      }
    },

    components:{
        CardItem,

    }
  }


</script>

<template>
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
