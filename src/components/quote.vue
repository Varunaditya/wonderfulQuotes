<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default">
      <div class="panel-body quote">
        <slot @click="console.log('a')"></slot>
      </div>
    </div>
  </div>
</template>

<script>

</script>

<style scoped>
  .panel-body {
    /*text-align: center;*/
    font-family: 'Arizonia', cursive;
    font-size: 24px;
    color: #6e6e6e;
  }

  .quote {
    cursor: pointer;
  }

  .quote:hover {
    background-color: lightcoral;
  }

</style>
