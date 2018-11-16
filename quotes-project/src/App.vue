<template>
  <div id="app">
    <div class="container">
      <div class="alert alert-danger" :class="{ hideMe: displayVal }" role="alert">
          Warning: You have {{ quotes.length }} quotes. The max allowed is {{ maxQuotes }}.
       </div>
      <quote-counter :quoteCount="quotes.length" :maxCount="maxQuotes"></quote-counter>
      <new-quote @newQuoteAdded="on_newQuoteAdded($event)"></new-quote>
      <quote-grid @quoteRemoved="on_quoteRemoved($event)" :quotes="quotes"></quote-grid>      
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
import QuoteCounter from "./components/QuoteCounter";

export default {
  name: "app",
  components: {
    QuoteGrid,
    NewQuote,
    QuoteCounter
  },  
  data: function() {
    return {
      quotes: ["First Quote - just filler"],
      maxQuotes: 10
    };
  },
  methods: {
    on_newQuoteAdded(e) {
      if (this.quotes.length < 10) {
        this.quotes.push(e);
      } 
    },
    on_quoteRemoved(e) {
      for (var i = 0; i < this.quotes.length; i++) {
        if (this.quotes[i] === e) {
          this.quotes.splice(i, 1);
        }
      }
    }
  }, 
  computed: {
    displayVal: function(){
      if (this.quotes.length < 9) return true;
      return false;
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.hideMe {
  display: none;
}
</style>

