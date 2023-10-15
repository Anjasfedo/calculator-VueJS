<script setup lang="js">
defineProps({
  result: {
    type: Number,
    required: true
  }
})
</script>

<template lang="html">
    <div class='h-24 border-2 border-rose-500 mb-2 relative'>
        <h1 class='absolute bottom-0 right-0 m-2 font-bold font-sans text-2xl'>{{ result }}</h1>
      </div>
</template>
  
<style lang="css">

</style>
