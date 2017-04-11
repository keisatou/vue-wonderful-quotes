<template>
  <div class="container">
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" :name="name"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';

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
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
  },
  components: {
    'app-quote-grid': QuoteGrid,
    'app-new-quote': NewQuote,
  },
};
</script>

<style>
</style>
