<template>
  <div>
    <header>
      <div class="wrapper">
        <button
          class="ham"
          :class="[isNavOpen ? 'nav-open' : '']"
          @click="toggleMenu($event, 'isNavOpen')"
        >
          Menu
        </button>
        <nav class="navbar">
          <ul :class="[isNavOpen ? 'nav-open' : '']">
            <li id="logo">
              <nuxt-link to="/">tom the dev</nuxt-link>
            </li>
            <li>
              <nuxt-link to="#">about</nuxt-link>
            </li>
            <li>
              <nuxt-link to="#">portfolio</nuxt-link>
            </li>
            <li>
              <nuxt-link to="#">blog</nuxt-link>
            </li>
            <li>
              <nuxt-link to="#" class="cta cta--small">contact me</nuxt-link>
            </li>
          </ul>
        </nav>
      </div>
    </header>
    <nuxt />
  </div>
</template>

<script>
export default {
  data() {
    return {
      isNavOpen: false
    }
  },
  methods: {
    toggleMenu(event) {
      this.isNavOpen = !this.isNavOpen
    }
  }
}
</script>

<style lang="scss">
html {
  font-family: 'CircularStd' 'Segoe UI', 'Candara', 'Bitstream Vera Sans',
    'DejaVu Sans', 'Bitsream Vera Sans', 'Trebuchet MS', 'Verdana',
    'Verdana Ref', sans-serif;
  font-size: 16px;
  word-spacing: 1px;
  -ms-text-size-adjust: 100%;
  -webkit-text-size-adjust: 100%;
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  box-sizing: border-box;
}

*,
*:before,
*:after {
  box-sizing: border-box;
  margin: 0;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-Book.ttf') format('truetype');
  font-weight: 300;
  font-style: normal;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-BookItalic.ttf') format('truetype');
  font-weight: 300;
  font-style: italic;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-Medium.ttf') format('truetype');
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-MediumItalic.ttf') format('truetype');
  font-weight: 500;
  font-style: italic;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-Bold.ttf') format('truetype');
  font-weight: bold;
  font-style: normal;
}

@font-face {
  font-family: 'CircularStd';
  src: url('~assets/fonts/CircularStd-Black.ttf') format('truetype');
  font-weight: 800;
  font-style: normal;
}

body {
  font-family: 'CircularStd', Georgia, serif;
  width: 100%;
}

h1 {
  font-weight: bold;
}

h2 span {
  font-weight: 800;
}

em {
  font-style: italic;
}

strong em {
  font-weight: bold;
  font-style: italic;
}

.full-bleed {
  width: 100vw;
  margin-left: calc(50% - 50vw);
}

.wrapper {
  margin-left: auto;
  margin-right: auto;
  max-width: 1040px;
  width: 90%;
}

header {
  background: white;
  padding: 2rem 0;
  & > .wrapper {
    display: flex;
    flex-direction: row-reverse;
  }
  @media only screen and (min-width: $tablet) {
    padding: 2.5rem 0;
    & > .wrapper {
      display: block;
    }
  }
}

.ham {
  &.nav-open {
    // position: absolute;
    // top: 20vh;
    // right: 10vw;
    z-index: 2;
  }
  @media only screen and (min-width: $tablet) {
    display: none;
  }
}

.navbar {
  margin: 0 auto;
  font-weight: 300;
  a {
    color: $dark;
    text-decoration: none;
  }
  ul {
    display: none;
    flex-direction: column;
    align-items: center;
    background: rgba(255, 255, 255, 0.95);
    list-style-type: none;
    padding: 0;
    &.nav-open {
      display: flex;
      position: absolute;
      padding: 20vh 0;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      z-index: 1;
      justify-content: space-around;
    }
    li a {
      padding: 0.5rem;
      &.cta--small {
        @include cta--small;
      }
    }
    @media only screen and (min-width: $tablet) {
      display: flex;

      flex-direction: row;
      #logo {
        margin-right: auto;
        a {
          padding: 0;
        }
      }
    }
    @media only screen and (min-width: $desktop) {
      padding: 1rem 1rem 1rem 0;
    }
  }
  @media only screen and (min-width: $tablet) {
    position: relative;
    height: auto;
  }
}

a.cta {
  @include cta;
  &--small {
    @include cta--small;
  }
}

section {
  margin: 0 auto;
  padding: 40px 0 4rem 0;
  @media only screen and (min-width: $lg-mobile) {
    padding: 60px 0 6rem 0;
  }
  @media only screen and (min-width: $tablet) {
    padding: 108px 0 12rem 0;
  }
  h1,
  h2 {
    margin-bottom: 10px;
    color: $dark;
    letter-spacing: 0.02rem;
    line-height: 1.1;
    font-weight: 400;
    font-size: 2.4rem;
    @media only screen and (min-width: $lg-mobile) {
      font-size: 2.75rem;
    }
    @media only screen and (min-width: $desktop) {
      font-size: 3.75rem;
      line-height: 102%;
    }
  }
}

@media only screen and (min-width: $desktop) {
  body {
    font-size: 18px;
  }
}
</style>
