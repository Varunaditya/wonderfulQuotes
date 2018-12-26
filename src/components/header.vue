<template>
  <div class="row">
    <div class="col-sm-12">
      <h3 :style="{'font-family': 'Arizonia, cursive', 'font-size': '50px'}">Wonderful Quotes</h3>
      <div class="progress">
        <div class="progress">
          <div class="progress-bar"
               role="progressbar"
               aria-valuenow="6"
               aria-valuemin="0"
               aria-valuemax="10"
               :style="{width: quotesCount * 10+ '%'}">
            <b>{{ quotesCount }} / 10</b>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: ['quotesCount']
  }
</script>
