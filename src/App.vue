<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
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
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: ["Just a quote to see something", "El saber", "Za DOm"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: QuoteGrid,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length < this.maxQuotes) {
        this.quotes.push(quote);
      } else {
        alert("Delete Quotes first!");
      }
    },
    delQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
};
</script>

<style>
</style>
