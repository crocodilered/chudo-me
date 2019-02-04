<template>
  <nav>
    <div class="button">
      <button
        class="menu-toggle"
        ref="menuToggleButton"
        @click="toggleMenu"
      >
        Menu
      </button>
    </div>
    <div
      class="menu-wrapper"
      ref="menuWrapper"
    >
      <router-link @click.native="closeMenu" to="/session">Фотосессии</router-link>
      <router-link @click.native="closeMenu" to="/calendar">Календари</router-link>
      <router-link @click.native="closeMenu" to="/book">Фотокниги</router-link>
      <router-link @click.native="closeMenu" to="/contacts">Контакты</router-link>
    </div>
  </nav>
</template>

<script>
  export default {
    name: 'Navigation',
    methods: {
      toggleMenu () {
        this.$refs.menuToggleButton.classList.toggle('active')
        this.$refs.menuWrapper.classList.toggle('active')
      },
      closeMenu () {
        this.$refs.menuToggleButton.classList.remove('active')
        this.$refs.menuWrapper.classList.remove('active')
      }
    }
  }
</script>

<style lang="scss">
  nav {
    padding: 7px 0 17px;
    background-color: #fff;
    opacity: .7;

    .menu-wrapper {
      a {
        font-family: 'Fira Sans Extra Condensed', sans-serif;
        font-weight: 300;
        color: #1B1B1B;
        white-space: nowrap;
        text-transform: uppercase;
        text-decoration: none;
        font-size: 16px;
      }

      a:hover {
        color: #d3408e!important;
        background: none;
      }
    }
  }

  @media (max-width: 420px) {
    /* Mobile */
    nav {
      background-color: #fff;
      opacity: .85;

      .menu-wrapper {
        padding: 0;

        max-height: 0;
        overflow-y: hidden;
        transition-property: all;
        transition-duration: .5s;
        transition-timing-function: cubic-bezier(0, 1, 0.5, 1);

        a {
          display: block;
          padding: 10px 20px;
        }
      }

      .menu-wrapper.active {
        max-height: 500px; /* approximate max height */
      }
    }
  }

  @media (min-width: 421px) {
    /* Desktop */
    nav {
      .button {
        display: none;
      }
      .menu-wrapper {
        display: block;
        a {
          margin: 0 2em;
        }
      }
    }
  }

  /* Button */
  $buttonWidth: 30px;
  $buttonHeight: 26px;
  $buttonColor: darken(#303030, 15%);
  $lineThickness: 4px;
  $transitionSpeed: .25s;
  $transitionEasing: ease-in-out;

  .button {
    text-align: center;
    margin-bottom: 10px;

    button.active {
      border-color: transparent;
      &:before {
        transform: translate(-50%, -50%) rotate(45deg);
      }
      &:after {
        transform: translate(-50%, -50%) rotate(-45deg);
      }
    }

    button {
      border: none;
      cursor: pointer;
      outline: none;
      position: relative;
      width: $buttonWidth;
      height: $buttonHeight;
      background: transparent;
      border-top: $lineThickness solid;
      border-bottom: $lineThickness solid;
      color: $buttonColor;
      font-size: 0;
      transition: all $transitionSpeed $transitionEasing;

      &:before,
      &:after {
        content: '';
        display: block;
        width: 100%;
        height: $lineThickness;
        position: absolute;
        top: 50%;
        left: 50%;
        background: currentColor;
        transform: translate(-50%, -50%);
        transition: transform $transitionSpeed $transitionEasing;
      }
    }
  }
</style>
