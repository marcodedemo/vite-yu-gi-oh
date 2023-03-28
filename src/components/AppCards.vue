<script>

    import store from "../store";

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
  <div>

    <CardItem></CardItem>
    
  </div>
</template>

<style lang="scss" scoped>

</style>
