<template>
    <div class="container">
      <quote-grid :quotes=quotes></quote-grid>
    </div>
</template>

<script>
    import quotegrid from './components/quoteGrid.vue';
    export default {
        data(){
          return {
            quotes: [
              'If you want something to be done then do it yourself.'
            ],
            maxQuotes: 10
          };
        },
        components: {
          quoteGrid: quotegrid
        }
    }
</script>

<style>
</style>
