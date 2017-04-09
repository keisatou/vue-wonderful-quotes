<template>
  <div class="container">
    <app-quote-grid :quotes="quotes" :name="name"></app-quote-grid>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';

export default {
  data() {
    return {
      name: 'app-quote-grid',
      quotes: [
        'Just a Quote to see something',
      ],
      maxQuotes: 10,
    };
  },
  components: {
    'app-quote-grid': QuoteGrid,
  },
};
</script>

<style>
</style>
