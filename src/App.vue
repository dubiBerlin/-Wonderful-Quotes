<template>
  <div class="container">
    <!-- EVENT vom Child zum Parent.
    Das Child Element appNewQuote feuert ein event namens 'quoteAdded' und gibt einen
    String damit zurück. App.vue hört somit auf das event und benutzt die eigene Methode 'newQuote'
    um diesen String abzufangen.-->
    <appNewQuote @quoteAdded="newQuote"></appNewQuote>
    <appQuoteGrid @quoteDeleted="delQuote" :quotes="quotes"></appQuoteGrid>
    <div class="col-sm-12 text-center">
      <div class="alert alert-info">Info: Click on a quote to delete it!</div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function() {
    return {
      quotes: ["Just a quote to see something", "El saber", "Za DOm"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
    delQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
