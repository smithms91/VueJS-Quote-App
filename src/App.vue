<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @removeQuote="removeQuote"></app-quote-grid>  
    <div class="info_box">
      <p>Info: Click on a quote to delete it.</p>
    </div>
  </div>
</template>

<script>
  import QuoteGrid from './components/QuoteGrid';
  import NewQuote from './components/NewQuote';
  import Header from './components/Header';

  export default {
    data: function() {
      return {
        quotes: ['The one and only.', 'The one and only.', 'The one and only.', 'The one and only.'],
        maxQuotes: 10
      }
    },
    methods: {
      newQuote(quote) {
        if(this.quotes.length >= 10) {
          return alert('Remove a quote before adding another!');
        }
        this.quotes.push(quote);
      },
      removeQuote(index) {
        this.quotes.splice(index, 1);
      }
    },
    components: {
      appQuoteGrid: QuoteGrid,
      appNewQuote: NewQuote,
      appHeader: Header
    }
  }
</script>

<style>
  * {
    margin: 0;
    padding: 0;
    border: none;
    outline: none;
    box-sizing: border-box;
  }

  body {
    background-color: #f2f2f2;
  }

  .container {
    max-width: 80%;
    margin: 0 auto;
  }

  .info_box {
    width: 100%;
    background-color: #a4e6f7;
    text-align: center;
    padding: .25rem;
  }
</style>
