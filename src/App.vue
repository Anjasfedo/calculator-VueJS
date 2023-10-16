<script setup lang="js">
import ShowNumberVue from './components/ShowNumber.vue';

import RowOne from './components/RowOne.vue';
import RowTwo from './components/RowTwo.vue';
import RowThree from './components/RowThree.vue';
import RowFour from './components/RowFour.vue';
import RowFive from './components/RowFive.vue';

import { ref, computed } from 'vue';

const input = ref([])

const result = ref(0)

const AddNumber = (num) => {
  input.value.push(num)
};

const Operation = (opt) => {
  const previousChar = input.value[input.value.length - 1];
  if (!isNaN(previousChar)) {
    input.value.push(opt);
  } else {
    console.error(false);
  }
}

const inputToString = computed(() => {
  return eval(input.value.join(''))
})

const DoOperation = () => {
  result.value = eval(input.value.join(''));
};

</script>

<template>
  <header>

  </header>

  <main class="flex flex-col items-center justify-center m-8">
    <div class=' border-2 border-rose-500'>
      {{ input }}

      {{ input.join('') }}

      {{ inputToString }}

    <ShowNumberVue :result="result"/>
      <div class='flex gap-3 flex-col'>
      <RowOne v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowTwo v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowThree v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFour v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFive v-bind:AddNumber="AddNumber" v-bind:DoOperation="DoOperation" />
      </div>
    </div>
  </main>
</template>

<style scoped>

</style>
