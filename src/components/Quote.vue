<template>
  <div class="col-sm-6 col-md-4 col-lg-3">
    <div class="panel panel-default text-center py-1">
      <div class="panel-body quote badge ma-1">
        <slot></slot>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .panel-body {
    font-family: 'Arizonia', cursive;
    font-size: 24px;
    color: green;
    border: 1px solid grey;
  }

  .quote {
    cursor: pointer;
  }

  .quote:hover {
    background-color: pink
  }
</style>
