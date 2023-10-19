<script setup lang="js">
import ShowNumberVue from './components/ShowNumber.vue';

import RowOne from './components/RowOne.vue';
import RowTwo from './components/RowTwo.vue';
import RowThree from './components/RowThree.vue';
import RowFour from './components/RowFour.vue';
import RowFive from './components/RowFive.vue';

import { ref, computed } from 'vue';

let input = ref([])

let result = ref(0);

const showResult = ref(false)

const AddNumber = (num) => {
  if (typeof num === 'number') {
    input.value.push(num)
  } else {
  const previousChar = input.value[input.value.length - 1];
  if (!isNaN(previousChar)) {
    input.value.push(num);
  } 
  }
  result.value = eval(input.value.join(''));
};

const Operation = (opt) => {
  const previousChar = input.value[input.value.length - 1];
  if (!isNaN(previousChar)) {
    input.value.push(opt);
  } else {
    console.error(false);
  }
}

const DoOperation = () => {
  showResult.value = true;
};

const clears = () => {
  input.value = [];
  result.value = 0;
  showResult.value = false;
}

const inputJoin = computed(() => {
  return input.value.join('')
})

</script>

<template>
  <header>

  </header>

  <main class="flex flex-col items-center justify-center m-8">
    <div class=' border-2 border-rose-500'>
      <!-- {{ input }}

      {{ inputJoin }}

      {{ result }} -->

    <ShowNumberVue :result="result" :inputJoin="inputJoin" :showResult="showResult"/>
      <div class='flex gap-3 flex-col'>
      <RowOne v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" :clears="clears" />
      <RowTwo v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowThree v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFour v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFive v-bind:AddNumber="AddNumber" v-bind:DoOperation="DoOperation" v-bind:Operation="Operation" />
      </div>
    </div>
  </main>
</template>

<style scoped>

</style>
