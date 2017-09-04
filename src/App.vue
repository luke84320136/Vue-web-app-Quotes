<template>
    <div class="container">
      <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
      <app-new-quote @addQuote="newQuote"></app-new-quote> <!-- 8/25 5.bind NewQuotes methods-->
      <app-quote-grid :quotes="quotes" @quoteDeleted="delQuote"></app-quote-grid>
      <!-- 8/25 7.Add delete button -->
      <div class="row">
        <div class="col-sm-12 text-center" >
          <div class="alert alert-info">
            提示：點擊記事即可刪除
          </div>
        </div>
      </div>
    </div>
</template>

<script>
    import QuoteGrid from './components/QuoteGrid.vue'
    import NewQuote from './components/NewQuote.vue' // 8/25 3.import NewQuote
    import Header from './components/Header.vue'

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
            if (this.quotes.length >= this.maxQuotes) {
              return alert ('請先刪除多餘的記事！')
            }
            this.quotes.push(quote)
          },
          delQuote (index) {
            this.quotes.splice(index, 1)
          }
        },
        components: {
          appQuoteGrid: QuoteGrid,
          appNewQuote: NewQuote, // 8/25 4. add components
          appHeader: Header
        }
    }
</script>

<style>
</style>
