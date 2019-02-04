<template>
  <div id="app">
    <div id="header">
      <div class="logo">
        <h1><router-link to="/">Chudo.me</router-link></h1>
        <div class="subtitle">Детская и семейная фотостудия</div>
      </div>
      <navigation/>
    </div>
    <router-view/>
    <footer>
      <div>
        <p>
          <a href="https://yandex.ru/maps/-/CBRpUMSfPD">
            Московская область,
            Красногорский район,
            поселок Петровский
          </a>
        </p>
        <P>
          <span><a href="tel:+7 (916) 211-16-69">+7 (916) 211-16-69</a></span>
          <span><a href="mailto:2111669@mail.ru">2111669@mail.ru</a></span>
          <span><a href="https://www.instagram.com/tayafoto/">Insta</a></span>
        </p>
      </div>
    </footer>
  </div>
</template>

<script>
  import Navigation from '@/components/common/navigation.vue'

  export default {
    name: 'App',
    components: { Navigation }
  }
</script>

<style lang="scss">

  @font-face {
    font-family: 'Vibes';
    src: url('~@/assets/fonts/goodvibescyr.woff') format('woff');
  }

  body {
    margin: 0;
    padding: 0;
    background: #f4f6f7;
    color: #000;
  }

  #app {
    font-family: Arial, 'Helvetica Neue', Helvetica, sans-serif;
    text-align: left;
  }

  hr {
    width: 60px;
    height: 0;
    background: 0;
    border: 0;
    border-bottom: 1px solid #ddd;
    margin: 40px auto;
  }

  hr.lo {
    margin: 0 auto;
  }

  div.resp-image {
    width: 100%;
  }

  p {
    margin: 0 auto 20px auto;
    color: #7F7F7F;
    font-family: 'Fira Sans Extra Condensed', sans-serif;
    font-size: 15px;
    line-height: 20px;
  }

  p.intro {
    text-align: center;
    width: 80%;
    max-width: 340px;
  }

  a {
    color: #a73370;
    text-decoration: none;
  }

  a:hover {
    color: #d3408e;
    background: #FEEEEF;
  }

  #header {
    z-index: 100;
    text-align: center;
    position: fixed;
    width: 100%;
    top: 0;

    .logo {
      padding: 20px 0 5px 0;
      background-color: #fff;

      h1 {
        font-family: 'Vibes', cursive;
        font-size: 56px;
        line-height: 56px;
        font-weight: 400;
        margin: 0;

        a {
          color: #303030;
          text-decoration: none;
        }

        a.router-link-exact-active {
          cursor: default;
        }
      }

      div.subtitle {
        font-family: 'Fira Sans Extra Condensed', sans-serif;
        padding: 4px 5px 3px;
        font-size: 12px;
        line-height: 12px;
        font-weight: 300;
        color: #525252;
        text-transform: uppercase;
        background-color: #FEEEEF;
        display: inline-block;
        letter-spacing: 1px;
        position: relative;
        top: -5px;
      }
    }
  }

  @media (max-width: 420px) {
    /* Mobile */
    .content {
      margin: 159px 10px 20px 10px;
    }
  }

  @media (min-width: 421px) {
    /* Desktop */
    .content {
      max-width: 1400px;
      margin: 0 auto;
      padding: 0 15px;
      margin-top: 151px;
    }

    footer {
      margin: 50px auto;

      div {
        text-align: center;

        span {
          margin-left: 1em;
          margin-right: 1em;
        }
      }
    }
  }
</style>
