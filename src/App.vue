<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <!-- Listen to event quoteAdded from selector's NewQuote.vue -->
        <app-new-quote @quoteAdded="newQuote"></app-new-quote>
      </div>
    </div>
    <!-- bind quote (initial name) to quote array => passing props -->

    <div>
      <app-quote-grid :quote="quotes"></app-quote-grid>
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

export default {
  data: function () {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10,
    };
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
  },
};
</script>

<style scoped>
</style>
