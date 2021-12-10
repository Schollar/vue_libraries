<template>
  <div @click="store_quote" class="quote_container">
    <p>{{ quote.quote }}</p>
    <h4>{{ quote.source }}</h4>
    <h6>{{ quote.philosophy }}</h6>
  </div>
</template>

<script>
import cookies from "vue-cookies";
export default {
  name: "page-quote",
  methods: {
    store_quote() {
      cookies.set("quote", this.quote);
    },
  },
  props: {
    quote: Object,
  },
};
</script>

<style scoped>
</style>