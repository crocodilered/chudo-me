<template>
  <div class="title-2">
    <div class="wrapper">
      <h2><slot></slot></h2>
      <div class="decor"></div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Title2'
  }
</script>

<style lang="scss">
  .title-2 {
    text-align: center;
    padding: 35px 0 20px;

    div.wrapper {
      display: inline-block;
    }

    h2 {
      font-family: 'Oswald', sans-serif;
      font-weight: 300;
      font-size: 26px;
      line-height: 26px;
      color: #303030;
      text-transform: uppercase;
      max-width: 100%;
      z-index: 10;
      position: relative;
      margin: 0 1.5em;
    }

    div.decor {
      border: 8px solid #FEEEEF;
      position: relative;
      top: -9px;
      z-index: 1;
    }
  }
</style>
