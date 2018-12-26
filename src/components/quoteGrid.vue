<template>
  <div class="row">
    <app-quote v-for="(quote, index) in quotes"
               @click.native="deleteQuote(index)">
      {{ quote }}
    </app-quote>
  </div>
</template>

<script>
  import quote from './quote.vue';
  import { eventBus } from "../main";
  export default {
    props: ['quotes'],
    components: {
      appQuote: quote
    },
    methods: {
      deleteQuote(index) {
        // console.log(index);
        eventBus.$emit('quoteWasDeleted', index);
      }
    }
  }
</script>

<style>

</style>
