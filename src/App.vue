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

<!-- klik na valutu treba da prikaže vrednost u EUR i kanadskim dolarima za kliknutu valutu u
novom prozoru (popup). Dakle, isto poziv ka apiju ali na klik valute. -->

