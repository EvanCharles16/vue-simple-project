<template>
  <div class="mt-5">
    <form>
      <div class="col-sm-8 col-xs-12 col-md-8 offset-md-2">
        <label for="quoteInput" class="font-weight-bold labelInput">
          <em>Quote</em>
        </label>
        <textarea id="quoteInput" class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-12 col-xs-12 col-md-8 offset-md-2 mb-5">
        <!-- OnClick Prevent => to prevent default , dont send request from the form to server, that will reload the page
        so That only execute the new method-->
        <button class="btn btn-primary btn-block mt-3 mb-3" @click.prevent="createNew">Add Quote</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      quote: "",
    };
  },
  methods: {
    createNew() {
      // This quote will be updated all the time because of binding it with two ways binding
      this.$emit("quoteAdded", this.quote);
      // Reset Quote after submitted or sent
      this.quote = "";
    },
  },
};
</script>

<style scoped>
.labelInput {
  font-size: 22px;
}
</style>
