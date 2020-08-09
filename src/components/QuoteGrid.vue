<template>
  <div class="row">
    <!-- Loop the quote array to HTML / BrowserView -->
    <!-- OnClick Native Modifier => react to click on that component -->
    <app-quote
      v-for="(quote, index) in quote"
      :key="quote"
      @click.native="deleteQuote(index)"
    >{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  // Catch the quote as a props from App.vue
  props: ["quote"],
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    },
  },
  components: {
    appQuote: Quote,
  },
};
</script>

<style>
</style>
