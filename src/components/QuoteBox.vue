<script setup>
import Shuffle from './icons/Shuffle.vue';
import Pause from './icons/Pause.vue';

defineProps(['quote', 'author']);
defineEmits(['randomQuote']);
</script>

<template>
  <div
    class="quote-item w-10/12 max-w-2xl m-auto rounded-xl py-8 px-6 relative"
  >
    <div class="quote text-center h-full">
      <h1 class="tracking-widest">{{ author }}</h1>
      <p>"{{ quote }}"</p>
    </div>

    <div class="icons">
      <div class="pause-icon">
        <Pause />
      </div>
      <div class="btn-random">
        <Shuffle @click="$emit('randomQuote')" class="cursor-pointer" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
