<template>
  <div class="container">
    <!-- Passing quoteCount property -->
    <app-header class="mt-5" :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <div class="row">
      <div class="col-md-12">
        <!-- Listen to event quoteAdded from selector's NewQuote.vue -->
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      </div>
    </div>
    <!-- bind quote (initial name) to quote array => passing props -->

    <div>
      <app-quote-grid :quote="quotes" @quoteDeleted="deleteQuote"></app-quote-grid>
    </div>
    <div class="row">
      <div class="col-sm-12 text-center mt-5">
        <div class="alert alert-info">Info : Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
import Header from "./components/Header";

export default {
  data: function () {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10,
      quoteCount: 0,
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete Quotes first");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    },
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header,
  },
};
</script>

<style scoped>
</style>
