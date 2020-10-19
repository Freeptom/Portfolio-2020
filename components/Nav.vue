<template>
  <header>
    <div class="wrapper">
      <button
        class="toggle"
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

.toggle {
  background: none;
  border: 2px solid $accent1;
  padding: 10px 24px;
  border-radius: $border-radius;
  box-shadow: none;
  color: $accent1;
  font-weight: bold;
  font-size: 1rem;
  text-transform: lowercase;
  transition: background-color 250ms ease;

  &:hover {
    cursor: pointer;
    background: $accent1;
    color: white;
  }

  &.nav-open,
  &:active {
    z-index: 2;
    opacity: 1;
    background: $accent1;
    color: white;
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
    display: block;
    opacity: 0;
    transition: opacity 500ms;
    position: absolute;
    top: -1000px;
    left: -1000px;
    flex-direction: column;
    align-items: center;
    background: rgba(255, 255, 255, 0.95);
    list-style-type: none;
    padding: 0;

    &.nav-open {
      opacity: 1;
      transition: opacity 250ms;
      display: flex;
      position: absolute;
      padding: 20vh 0;
      top: 0;
      left: 0;
      height: 100%;
      width: 100%;
      z-index: 1;
      justify-content: space-between;
    }
    li a {
      font-size: 1.5rem;
      padding: 0.5rem;
      &.cta--small {
        @include cta--small;
      }
    }
    @media only screen and (min-width: $tablet) {
      position: relative;
      top: 0;
      left: 0;
      display: flex;
      opacity: 1;
      flex-direction: row;
      #logo {
        margin-right: auto;
        a {
          padding: 0;
        }
      }
      li a {
        font-size: 1rem;
      }
      @media only screen and (min-width: $desktop) {
        li a {
          font-size: 1.125rem;
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
</style>
