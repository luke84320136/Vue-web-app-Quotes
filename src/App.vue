<template>
    <div class="container">
      <app-new-quote @addQuote="newQuote"></app-new-quote> <!-- 8/25 5.bind NewQuotes methods-->
      <app-quote-grid :quotes="quotes"></app-quote-grid>
      <!-- 8/25 7.Add delete button -->
      <!-- <div class="row">
        <div class="col-sm-12">

        </div>
      </div> -->
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue'
    import NewQuote from './components/NewQuote.vue' // 8/25 3.import NewQuote

    export default {
        data () {
          return {
            quotes: [
              'Quote Here'
            ],
            maxQuotes: 10
          }
        },
        methods: {
          // 8/25 6. newQuote methods，新增quote至quotes
          newQuote (quote) {
            this.quotes.push(quote)
          }
        },
        components: {
          appQuoteGrid: QuoteGrid,
          appNewQuote: NewQuote // 8/25 4. add components
        }
    }
</script>

<style>
</style>
