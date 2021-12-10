b<template>
  <div>
    <button-one @button_clicked="display_quotes"></button-one>
    <page-quote
      v-for="quote in quotes"
      :key="quote._id"
      :quote="quote"
    ></page-quote>
  </div>
</template>

<script>
import ButtonOne from "./ButtonOne.vue";
import PageQuote from "./PageQuote.vue";
export default {
  name: "home-content",
  methods: {
    display_quotes(payload) {
      this.quotes = payload;
    },
  },
  data() {
    return {
      quotes: [],
    };
  },
  components: {
    ButtonOne,
    PageQuote,
  },
};
</script>

<style scoped>
</style>