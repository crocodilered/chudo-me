<template>
  <h4><slot></slot></h4>
</template>

<script>
  export default {
    name: 'Title4'
  }
</script>

<style lang="scss">
  h4 {
    font-family: 'Fira Sans Extra Condensed', sans-serif;
    font-weight: 200;
    font-size: 14px;
    color: #7F7F7F;
    text-align: center;
    margin: 20px 0;
  }
</style>
