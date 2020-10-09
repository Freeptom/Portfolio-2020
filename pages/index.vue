<template>
  <div class="wrapper">
    <section class="intro">
      <div>
        <h1>Finally, a website your users will love.</h1>
        <p class="intro__sub-heading">
          I’m Tom Pearson – builder of <strong>beautiful</strong>,
          <strong>bespoke</strong> and <strong>accessible</strong> websites for
          clients big and small.
        </p>
        <nuxt-link to="#" class="cta">View my Work</nuxt-link>
      </div>
      <div class="intro__image-wrapper">
        <img src="~/assets/images/laptop.svg" />
      </div>
    </section>

    <div class="wrapper">
      <section class="how full-bleed">
        <div class="wrapper">
          <h2>How I can help <span>you</span>.</h2>
          <ul class="card-list">
            <li v-for="skill in Skills" :key="skill.heading" class="card">
              <card-item
                :heading="skill.heading"
                :desc="skill.desc"
                :iconfile="skill.icon"
                :herofile="skill.hero"
              >
                ></card-item
              >
            </li>
          </ul>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import CardItem from '../components/CardItem.vue'
export default {
  components: {
    CardItem
  },
  data() {
    return {
      title: 'Tom the Web Developer',
      Skills: [
        {
          heading: 'Tailored for you',
          desc: 'test',
          hero: 'tailored.jpg',
          icon: 'create.svg'
        },
        {
          heading: 'Create a Vue project with the CLI',
          desc: 'test',
          hero: 'tailored.jpg',
          icon: 'create.svg'
        },
        {
          heading: 'Have fun',
          desc: 'test',
          hero: 'tailored.jpg',
          icon: 'create.svg'
        }
      ]
    }
  },
  head() {
    return {
      title: this.title,
      meta: [
        // hid is used as unique identifier. Do not use `vmid` for it as it will not work
        {
          hid: 'description',
          name: 'description',
          content: 'The portfolio for freelance web developer, Tom Pearson'
        }
      ]
    }
  }
}
</script>

<style lang="scss">
.intro {
  position: relative;
  display: flex;
  flex-wrap: wrap;
  h1 {
    max-width: 40ch;
  }
  @media only screen and (min-width: $desktop) {
    flex-wrap: nowrap;
    h1 {
      max-width: 20ch;
    }
  }
  &__sub-heading {
    font-weight: 300;
    font-size: 1.2rem;
    max-width: 45ch;
    color: $grey1;
    letter-spacing: 0.02rem;
    margin: 0 0 1.75rem 0;
    @media only screen and (min-width: $desktop) {
      font-size: 1.5rem;
      margin: 0 0 2.5rem 0;
    }
  }
  &__image-wrapper {
    position: relative;
    width: auto;
    @media only screen and (min-width: $tablet) {
      margin: 4rem auto;
    }
    @media only screen and (min-width: $desktop) {
      margin: 0;
    }
    img {
      z-index: 1;
      align-self: center;
      width: 100%;
      max-width: 200px;
      height: auto;
      display: none;
      @media only screen and (min-width: $tablet) {
        max-width: 385px;
        display: block;
        align-self: flex-end;
      }
    }
    &::before {
      content: '';
      position: absolute;
      top: -40px;
      right: -40px;
      z-index: -1;
      border: 10px solid $primary-color;
      height: 150px;
      width: 150px;
      border-radius: 50%;
      @media only screen and (min-width: $tablet) {
        height: 272px;
        width: 272px;
        top: -100px;
        right: -80px;
        border: 20px solid $primary-color;
      }
    }
  }
  &::after {
    content: '';
    position: absolute;
    bottom: 15vh;
    right: 25vw;
    z-index: -1;
    background: $neutral;
    height: 54px;
    width: 54px;
    border-radius: 50%;
  }
}

.how {
  background: $primary-color-lighter;
  background-image: linear-gradient(
      0deg,
      $primary-color-darker 10%,
      rgba(61, 64, 91, 0.8)
    ),
    url('~assets/images/sprinkle.svg');

  background-repeat: no-repeat, no-repeat;
  background-size: cover;
  position: relative;
  h2 {
    color: white;
    // background: rgba(26, 46, 40, 0.5);
  }
  &::before {
    content: '';
    position: absolute;
    top: -8vh;
    right: 12vw;
    z-index: -1;
    background: $accent2;
    height: 126px;
    width: 126px;
    border-radius: 50%;
    @media only screen and (min-width: $tablet) {
      right: 60vw;
    }
    @media only screen and (min-width: $desktop) {
      right: 12vw;
    }
  }
}

.card-list {
  padding: 0;
  list-style: none;
  display: flex;
  justify-content: flex-start;
  flex-wrap: wrap;
  @media only screen and (min-width: $tablet) {
    justify-content: center;
    margin: 4rem 0;
  }
  .card {
    background: white;
    border-radius: $border-radius;
    margin: 1rem;
    @media only screen and (min-width: $tablet) {
      max-width: 30%;
    }
    .hero-container {
      &__image {
        border-radius: $border-radius $border-radius 0 0;
        width: 100%;
        height: 100px;
        object-fit: cover;
        @media only screen and (min-width: $lg-mobile) {
          height: 180px;
        }
        @media only screen and (min-width: $tablet) {
          height: 200px;
        }
      }
    }
    .card-content {
      padding: 1rem;
    }
  }
}
</style>
