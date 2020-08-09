<template>
  <div class="row">
    <!-- Loop the quote array to HTML / BrowserView -->
    <app-quote v-for="quote in quote" :key="quote">{{ quote }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote";
export default {
  // Catch the quote as a props from App.vue
  props: ["quote"],
  components: {
    appQuote: Quote,
  },
};
</script>

<style>
</style>
