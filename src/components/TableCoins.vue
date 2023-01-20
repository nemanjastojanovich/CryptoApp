<template>
  <div class="tableCoins">
    <table>
      <tr>
        <td>Name</td>
        <td>Value</td>
        <td>Market cap</td>
      </tr>
      <tr v-for="coin in coins">
        <td  @click="popUp">
          {{ coin.name }}
        </td>
        <td>
          {{ coin.current_price }} USD
        </td>
        <td>
          {{ coin.market_cap }}
        </td>
      </tr>
    </table>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits (['finish'], ['popup'])
let coins = ref ([]);


fetch(
  "https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=10&page=1&sparkline=false"
)
  .then((resp) => resp.json())
  .then((result) => {
    coins.value = result
    console.log(result)
    // coins.value.id = ID
    // console.log(ID)
    setTimeout (function () {emit('finish')},2000)
    });
    
    function popUp() {
      console.log("aaaa")
      
    }

    

</script>
