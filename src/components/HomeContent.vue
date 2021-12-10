b<template>
  <div>
    <button-one @button_clicked="display_quotes"></button-one>
    <section
      @click="store_quote"
      v-for="quote in quotes"
      :key="quote._id"
      :source="quote.source"
    >
      <h1>{{ quote.source }}</h1>
      <h1>{{ quote.quote }}</h1>
    </section>
  </div>
</template>

<script>
import ButtonOne from "./ButtonOne.vue";
import cookies from "vue-cookies";
export default {
  name: "home-content",
  methods: {
    display_quotes(payload) {
      this.quotes = payload;
      return this.quotes;
    },
    store_quote(quote) {
      console.log(quote);
      cookies.set("quote", quote.srcElement.innerText);
    },
  },
  data() {
    return {
      quotes: {},
    };
  },
  components: {
    ButtonOne,
  },
};
</script>

<style scoped>
</style>