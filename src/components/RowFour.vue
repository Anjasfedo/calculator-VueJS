<script setup lang="js">

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
import { fas } from '@fortawesome/free-solid-svg-icons';

defineProps({
  Operation: {
    type: Function,
  },
  AddNumber: {
    type: Function,
  }
})

const icons = {
  fa1: fas.fa1,
  fa2: fas.fa2,
  fa3: fas.fa3,
  faPlus: fas.faPlus,
};
</script>


<template lang="html">
  <div class="flex flex-row justify-between w-full gap-2">
    <button @click="AddNumber(1)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa1" />
    </button>
    <button @click="AddNumber(2)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa2" />
    </button>
    <button @click="AddNumber(3)" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa3" />
    </button>
    <button @click="Operation('+')" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.faPlus" />
    </button>
  </div>
</template>

  
<style lang="css">

</style>
