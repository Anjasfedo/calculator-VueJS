<script setup lang="js">

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { fas } from '@fortawesome/free-solid-svg-icons';

defineProps({
  Operation: {
    type: Object,
  },
  AddNumber: {
    type: Object,
  }
})

const icons = {
  fa4: fas.fa4,
  fa5: fas.fa5,
  fa6: fas.fa6,
  faMinus: fas.faMinus,
};
</script>


<template lang="html">
  <div class="flex flex-row justify-between w-full gap-2">
    <button @click="AddNumber(4)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa4" />
    </button>
    <button @click="AddNumber(5)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa5" />
    </button>
    <button @click="AddNumber(6)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa6" />
    </button>
    <button @click="Operation('-')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.faMinus" />
    </button>
  </div>
</template>

  
<style lang="css">

</style>
