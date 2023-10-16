<script setup lang="js">
import ShowNumberVue from './components/ShowNumber.vue';

import RowOne from './components/RowOne.vue';

import RowTwo from './components/RowTwo.vue';

import RowThree from './components/RowThree.vue';
import RowFour from './components/RowFour.vue';
import RowFive from './components/RowFive.vue';

import { ref, computed, watch   } from 'vue';

const numbers = ref(0)

const input = ref([])

const operations = ref('')

const AddNumber = (num) => {
  input.value.push(num)
};

const Operation = (opt) => {
  updateComputedResult();
  const previousChar = input.value[input.value.length - 1];
  if (!isNaN(previousChar)) {
    // Jika operator sebelumnya adalah angka, maka tambahkan operator
    input.value.push(opt);
  } else {
    // Operator sebelumnya bukan angka, mungkin Anda ingin menangani kasus ini.
    console.error(false);
  }
  
}

const computedResult = ref(0);

const updateComputedResult = () => {
  computedResult.value = evaluateExpression(input.value);
};

const DoOperation = () => {
  updateComputedResult();
  // Do something with the computed result, e.g., display or save it
  console.log('Hasil operasi:', computedResult.value);
};

const evaluateExpression = (expression) => {
  let numStack = [];
  let opStack = [];
  let num = 0;

  for (const token of expression) {
    if (!isNaN(token)) {
      num = num * 10 + token;
    } else if (['+', '-', 'x', '/'].includes(token)) {
      numStack.push(num);
      num = 0;

      while (
        opStack.length > 0 &&
        precedence(opStack[opStack.length - 1]) >= precedence(token)
      ) {
        numStack.push(
          performOperation(opStack.pop(), numStack.pop(), numStack.pop())
        );
      }

      opStack.push(token);
    }
  }

  numStack.push(num);

  while (opStack.length > 0) {
    numStack.push(
      performOperation(opStack.pop(), numStack.pop(), numStack.pop())
    );
  }

  return numStack[0];
};

const precedence = (operator) => {
  if (operator === 'x' || operator === '/') {
    return 2;
  }
  if (operator === '+' || operator === '-') {
    return 1;
  }
  return 0;
};

const performOperation = (operator, b, a) => {
  switch (operator) {
    case '+':
      return a + b;
    case '-':
      return a - b;
    case 'x':
      return a * b;
    case '/':
      return a / b;
  }
};

watch(input, () => {
  updateComputedResult();
});

</script>

<template>
  <header>

  </header>

  <main class="flex flex-col items-center justify-center m-8">
    <div class=' border-2 border-rose-500'>
      {{ input }}
      {{ computedResult }}

      
    <ShowNumberVue v-bind:result="computedResult" />
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
