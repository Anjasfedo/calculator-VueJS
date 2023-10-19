<script setup lang="js">
defineProps({
  result: {
    type: Number,
    required: true
  },
  inputJoin: {
    type: String,
    required: true
  },
  showResult: {
    type: Boolean,
    required: true,
  }
})
</script>

<template lang="html">
    <div class='h-24 border-2 border-rose-500 mb-2 relative'>
        <div class="w-full">
          <div v-if="!showResult" class="w-full">
            <h1 class='absolute top-0 right-0 m-2 font-bold font-sans text-2xl'>{{ inputJoin }}</h1>
            <h1 class='absolute bottom-0 right-0 m-2 font-bold font-sans text-2xl'>{{ result }}</h1>
          </div>
          <div v-else>
            <h1 class='absolute bottom-0 right-0 m-2 font-bold font-sans text-6xl'>{{ result }}</h1>
          </div>
        </div>
      </div>
</template>
  
<style lang="css">

</style>
