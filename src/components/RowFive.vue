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
  DoOperation: {
    type: Function,
  },

})


const icons = {
  fa0: fas.fa0,
  faCircle: fas.faCircle,
  faEquals: fas.faEquals,
};
</script>


<template lang="html">
  <div class="flex flex-row justify-between w-full gap-2">
    <button @click="AddNumber(0)" class='bg-pink-400 rounded-full w-40 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.fa0" />
    </button>
    <button class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center relative'>
      <font-awesome-icon :icon="icons.faCircle" size="2xs" class="absolute bottom-7"/>
    </button>
    <button @click="DoOperation()" class='bg-pink-400 rounded-full w-20 h-20 flex items-center justify-center'>
      <font-awesome-icon :icon="icons.faEquals" />
    </button>
  </div>
</template>

  
<style lang="css">

</style>
