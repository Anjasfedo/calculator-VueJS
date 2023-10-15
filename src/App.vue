<script setup lang="js">
import ShowNumberVue from './components/ShowNumber.vue';

import RowOne from './components/RowOne.vue';

import RowTwo from './components/RowTwo.vue';

import RowThree from './components/RowThree.vue';
import RowFour from './components/RowFour.vue';
import RowFive from './components/RowFive.vue';

import { ref } from 'vue';

const numbers = ref(0)

const firstNumber = ref([]);

const secondNumber = ref([])

const operations = ref('')

// const result = ref(0)


const AddNumber = (num) => {
  (!operations.value) ? firstNumber.value.push(num) : secondNumber.value.push(num);
};

const Operation = (opt) => {
  operations.value = opt;
  // operation.value.push(operations);
}

const DoOperation = (firstNumber, secondNumber) => {
  const firstNumberAsString = firstNumber.join(''); // Menggabungkan elemen array menjadi string
  const secondNumberAsString = secondNumber.join(''); // Menggabungkan elemen array menjadi string
  
  const firstNumberAsNumber = parseInt(firstNumberAsString, 10); // Mengonversi string menjadi angka
  const secondNumberAsNumber = parseInt(secondNumberAsString, 10); // Mengonversi string menjadi angka

  numbers.value = firstNumberAsNumber + secondNumberAsNumber; // Melakukan operasi matematika
}


</script>

<template>
  <header>

  </header>

  <main class="flex flex-col items-center justify-center m-8">
    <div class=' border-2 border-rose-500'>
      {{ firstNumber }} {{ operations }} {{ secondNumber }} 
      <!-- {{ firstNumber.reduce((acc, num) => acc + num, 0) + secondNumber.reduce((acc, num) => acc + num, 0) }} -->

      
    <ShowNumberVue v-bind:result="numbers" />
      <div class='flex gap-3 flex-col'>
      <RowOne v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowTwo v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowThree v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFour v-bind:AddNumber="AddNumber" v-bind:Operation="Operation" />
      <RowFive v-bind:AddNumber="AddNumber" v-bind:DoOperation="DoOperation" :firstNumber="firstNumber" :operation="operation" :secondNumber="secondNumber" />
      </div>
    </div>
  </main>
</template>

<style scoped>

</style>
