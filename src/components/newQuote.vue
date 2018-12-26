<template>
  <div class="row">
    <form>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <label>Quote</label>
        <textarea class="form-control"
                  rows="3"
                  v-model="newQuote">

        </textarea>
      </div>
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group">
        <button class="btn-primary btn"
                @click.prevent="addNewQuote">
          Add Quote
        </button>
      </div>
    </form>
  </div>
</template>

<script>
  import { eventBus } from "../main";
  export default {
    data(){
      return {
        newQuote: ''
      };
    },
    methods: {
      addNewQuote() {
        eventBus.$emit('newQuoteAdded', this.newQuote);
        this.newQuote = '';
      }
    }
  }
</script>

<style>

</style>
