<template>
  <div class="col-xs-12 col-md-6 col-lg-4">
    <div class="card mt-5 text-center" style="width: 18rem;">
      <div class="card-body quote">
        <!-- Slot =>  the quote content passed from outside (content = QuoteGrid.vue) -->
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.card-body {
  font-family: "Arizonia", cursive;
  font-size: 24px;
  color: #6e6e6e;
}

.quote {
  cursor: pointer;
}

.quote:hover {
  background-color: #ffe2e2;
}
</style>
