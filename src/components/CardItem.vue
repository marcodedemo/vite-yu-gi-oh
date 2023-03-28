<script>

    import {store} from '../store';


  export default{
    data(){
      return{
        
        store,

      }
    },

    props: {
        cardName: String,
        image: String,
        cardType: String,

    }
  }


</script>

<template>
  <div class="card">

    <img :src="image" alt="card image">

    <div id="card-info">

        <strong>{{ cardName }}</strong>
        <span> <strong>Type:</strong> {{ cardType }}</span>
          
    </div>
    
  </div>
</template>

<style lang="scss" scoped>

.card{
    display: flex;
    flex-direction: column;

    width: calc(100% / 5 - 20px * 6 / 5);

    img{
        width: 100%;
    }

    #card-info{
        display: flex;
        align-items: center;
        flex-direction: column;
    }
}

</style>
