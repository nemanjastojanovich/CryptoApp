<script setup>
  import TableCoins from '@/components/TableCoins.vue';
  import Loader from '@/components/Loader.vue';
  import PopUp from '@/components/PopUp.vue';
  import { ref } from "vue";
  let isLoaded = ref (false)
  let isClicked = ref (false)
  function finishLoader() {
    isLoaded.value=true
  }

</script>

<template>
  <div class="cryptoApp">
    <Loader v-show="!isLoaded"/>
    <TableCoins @finish="finishLoader" v-show="isLoaded"/>
    <PopUp v-show="isLoaded"/>
    
  </div>
</template>

<style scoped lang="scss">

</style>



