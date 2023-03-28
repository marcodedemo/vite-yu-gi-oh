<script>

  import store from "../src/store";

  import AppCards from "./components/AppCards.vue";

  export default{
    data(){
      return{

        store,
        

      }
    },

    components:{
      AppCards,
    }

  }

  


</script>

<template>
  <div>

    <AppCards></AppCards>
    
  </div>
</template>

<style lang="scss" scoped>

</style>
