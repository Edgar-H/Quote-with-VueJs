<script setup>
import { ref } from 'vue';
import { quotes } from '@/assets/quotes.json';
import { getRandomNumber } from '@/assets/RandomColor.js';
import QuoteBox from '@/components/QuoteBox.vue';

const cunterQuote = quotes.length;
const quote = ref({});

const randomQuote = () => {
  const quoteRandom = quotes[getRandomNumber(cunterQuote)];
  quote.value = quoteRandom;
};

randomQuote();
</script>

<template>
  <main class="app h-screen w-screen flex">
    <QuoteBox
      :quote="quote.quote"
      :author="quote.author"
      @randomQuote="randomQuote"
    />
  </main>
</template>
