<template>
    <div class="row">
      <div class="col-sm-12">
        <h3>增加記事</h3>
        <div class="progress">
          <div class="progress-bar" role="progressbar" aria-valuenow="60"
            :style="{進度： (quoteCount/maxQuotes) * 100 + '%'}">
            {{ quoteCount }} / {{ maxQuotes }}
          </div>
        </div>
      </div>
    </div>
</template>
<script>
  props: ['quoteCount', 'maxQuotes']
</script>
