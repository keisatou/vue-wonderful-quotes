<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" :name="name" @quoteDeleted="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from './components/QuoteGrid.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

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
    newQuote(quote) { // eslint-disable-line consistent-return
      if (this.quotes.length >= this.maxQuotes) {
        return alert('Please delete Quotes first!'); // eslint-disable-line no-alert,no-undef
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
  components: {
    'app-quote-grid': QuoteGrid,
    'app-new-quote': NewQuote,
    'app-header': Header,
  },
};
</script>

<style>
</style>
