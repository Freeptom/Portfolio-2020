<template>
  <div>
    <header>
      <div class="wrapper">
        <div class="navbar">
          <nuxt-link to="/">tom the dev</nuxt-link>
          <nav>
            <ul>
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
      </div>
    </header>
    <nuxt />
  </div>
</template>

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
  src: url('~assets/fonts/CircularStd-Bold.ttf') format('truetype');
  font-weight: bold;
  font-style: normal;
}

body {
  font-family: 'CircularStd', Georgia, serif;
  width: 100%;
}

h1 {
  font-weight: bold;
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
  padding: 2.5rem 0;
}

.navbar {
  margin: 0 auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  font-weight: 300;
  a {
    color: $dark;
    text-decoration: none;
  }
  nav {
    display: flex;
    ul {
      list-style-type: none;
      padding: 0;
      display: flex;
      li a {
        padding: 0.5rem;
        &.cta--small {
          @include cta--small;
        }
      }
      @media only screen and (min-width: $desktop) {
        padding: 1rem;
      }
    }
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
