<script>

import {store} from '../store';


  export default{

    data() {
      return {

        store,


      }
    },


  }


</script>



<template>
  <div>
    <div id="testo">Sono state generate {{ this.store.generatedCardNumber }} carte</div>
  </div>
</template>




<style lang="scss" scoped>

#testo{
  text-align: center;
}

</style>
