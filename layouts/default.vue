<template>
  <div>
    <Nav></Nav>
    <nuxt />
  </div>
</template>

<script>
import Nav from '../components/Nav.vue'

export default {
  components: {
    Nav
  },
  data() {
    return {}
  },
  methods: {}
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
    padding: 60px 0 12rem 0;
  }
  @media only screen and (min-width: $tablet) {
    padding: 80px 0 8rem 0;
  }
  @media only screen and (min-width: $desktop) {
    padding: 108px 0 12rem 0;
  }
  h1,
  h2 {
    margin-bottom: 10px;
    color: $dark;
    letter-spacing: 0.02rem;
    line-height: 1.1;
    font-weight: 400;
  }
  h1 {
    font-size: 2.2rem;
    @media only screen and (min-width: $lg-mobile) {
      font-size: 2.75rem;
    }
    @media only screen and (min-width: $desktop) {
      font-size: 3.75rem;
      line-height: 102%;
    }
  }
  h2 {
    font-size: 2rem;

    @media only screen and (min-width: $lg-mobile) {
      font-size: 2.75rem;
    }
    @media only screen and (min-width: $desktop) {
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
