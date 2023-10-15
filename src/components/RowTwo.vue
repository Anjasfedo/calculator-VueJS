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
  fa7: fas.fa7,
  fa8: fas.fa8,
  fa9: fas.fa9,
  faXmark: fas.faXmark,
};
</script>


<template lang="html">
  <div class="flex flex-row justify-between w-full gap-2">
    <button @click="AddNumber(7)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa7" />
    </button>
    <button @click="AddNumber(8)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa8" />
    </button>
    <button @click="AddNumber(9)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa9" />
    </button>
    <button @click="Operation('x')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.faXmark" />
    </button>
  </div>
</template>

  
<style lang="css">

</style>
