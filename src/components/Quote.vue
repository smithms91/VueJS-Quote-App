<template>
      <div class="panel-body quote">
        <slot></slot>
      </div>
</template>

<script>

</script>

<style>
  .panel-body {
    font-size: 24px;
    color: #6e6e6e;
    padding: 2rem;
    border: 1px solid black;
    margin: 1rem;
  }

  .quote {
    cursor: pointer;
  }

  .quote:hover {
    background-color: #ffe2e2;
  }
</style>

