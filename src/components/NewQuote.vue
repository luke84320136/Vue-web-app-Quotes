<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Quote</label>
        <textarea class="form-control" rows="3" v-model="quote"></textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
      <button class="btn btn-primary" @click.prevent="createNew">新增Quote</button> <!-- 8/25 1.v-bind createNew methods, prevent防reload -->
      </div>
    </form>

  </div>
</template>

<script>
export default {
  // set up quotes
  data () {
    return {
      quote: ''
    }
  },
  // 8/25 2. Add New quote methods
  methods: {
    createNew () {
      this.$emit('addQuote', this.quote) //Back to App.vue
      this.quote = ''
    }
  }
  }
</script>
