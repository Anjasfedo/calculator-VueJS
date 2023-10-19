<script setup lang="js">

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { fas } from '@fortawesome/free-solid-svg-icons';

defineProps({
  Operation: {
    type: Function,
  },
  AddNumber: {
    type: Function,
  },
  clears: {
    type: Function,
  }
})

const icons = {
  faA: fas.faA,
  faC: fas.faC,
  plusMinus: fas.faPlusMinus,
  percent: fas.faPercent,
  divide: fas.faDivide,
};
</script>


<template lang="html">
  <div class="flex flex-row justify-between w-full gap-2">
    <button @click="clears" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.faA" />
      <font-awesome-icon :icon="icons.faC" />
    </button>
    <button @click="Operation('+-')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.plusMinus" />
    </button>
    <button @click="Operation('%')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.percent" />
    </button>
    <button @click="Operation('/')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.divide" />
    </button>
  </div>
</template>

  
<style lang="css">

</style>
