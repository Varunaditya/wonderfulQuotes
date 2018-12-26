<template>
    <div class="container">
      <app-header :quotesCount=quotesNumber></app-header>
      <new-quote></new-quote>
      <quote-grid :quotes=quotes></quote-grid>
      <div class="row">
        <div class="col-sm-12 text-center">
          <div class="alert-info alert">Click on a quote to delete it.</div>
        </div>
      </div>
    </div>
</template>

<script>
    import quotegrid from './components/quoteGrid.vue';
    import newquote from './components/newQuote.vue';
    import header from './components/header.vue';
    import { eventBus } from "./main";
    export default {
        data(){
          return {
            quotes: [
              "If you want something to be done then do it yourself.",
              "You either die a hero or live long enough to see yourself becoming the villain."
            ],
            quotesNumber: 2
          };
        },
        components: {
          quoteGrid: quotegrid,
          newQuote: newquote,
          appHeader: header
        },
        created() {
          eventBus.$on('newQuoteAdded', (data) => {
            if(this.quotesNumber < 10){
              this.quotes.push(data);
              this.quotesNumber += 1;
            }
          });
          eventBus.$on('quoteWasDeleted', (index) => {
            this.quotes.splice(index, 1);
            this.quotesNumber -= 1;
          });

        }
    }
</script>

<style>
</style>
