<template>
  <div class="row">
    <appQuote v-for="quote in quotes" :key="quote">{{quote}}</appQuote>
  </div>
</template>

<script>
import Quote from "./Quote";

export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  }
};
</script>

<style>
</style>
