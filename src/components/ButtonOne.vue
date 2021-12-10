<template>
  <button @click="get_quotes">Click Me</button>
</template>

<script>
import axios from "axios";
export default {
  name: "button-one",
  methods: {
    get_quotes() {
      axios
        .request({
          url: "http://philosophy-quotes-api.glitch.me/quotes",
        })
        .then((response) => {
          this.$emit("button_clicked", response.data);
        })
        .catch((error) => {
          error;
          this.$emit(
            "button_clicked",
            "Sorry, there was an error with the API"
          );
        });
    },
  },
};
</script>

<style scoped>
</style>