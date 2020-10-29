<template>
  <div class="wrapper">
    <section class="intro">
      <div>
        <h1>Finally, a website users will love.</h1>
        <p class="intro__subheading">
          I’m Tom Pearson &#8212; builder of
          <strong>beautiful</strong>, <strong>bespoke</strong> and
          <strong>accessible</strong> websites.
        </p>
        <div class="cta-container">
          <nuxt-link to="#" class="cta--alt">My Work</nuxt-link>
          <nuxt-link to="#" class="cta">Let's chat</nuxt-link>
        </div>
      </div>
      <div class="intro__image-wrapper">
        <img src="~/assets/images/laptop.svg" />
      </div>
    </section>

    <div class="wrapper">
      <section class="how full-bleed">
        <div class="wrapper">
          <p class="mini-heading">your home on the web</p>
          <h2>How I can help you.</h2>
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

    <div class="wrapper">
      <section class="work full-bleed">
        <div class="wrapper">
          <p class="mini-heading">Join the list</p>
          <h2>A few of the good folks I've worked with</h2>
          <ul class="logo-list">
            <li v-for="logo in Logos" :key="logo.id">
              <logo :logo="logo.image"></logo>
            </li>
          </ul>
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import CardItem from '../components/CardItem.vue'
import Logo from '../components/Logo.vue'
export default {
  components: {
    CardItem,
    Logo
  },
  data() {
    return {
      title: 'Tom the Web Developer',
      Skills: [
        {
          heading: 'Creative mind',
          desc:
            "No, just a regular mistake. Oh, how I wish I could believe or understand that! There's only one reasonable course of action now: kill Flexo!",
          hero: 'creative.svg'
        },
        {
          heading: 'People-centred development',
          desc:
            "Good news, everyone! I've taught the toaster to feel love! Hey, what kinda party is this? Dr. Zoidberg, that doesn't make sense.",
          hero: 'detail.svg'
        },
        {
          heading: 'Experience in Consultancy',
          desc:
            "With a warning label this big, you know they gotta be fun! You can crush me but you can't crush my spirit! Ask her how her day was.",
          hero: 'creative.svg'
        }
      ],
      Logos: [
        {
          image: 'vodafone.png'
        },
        {
          image: 'arla.png'
        },
        {
          image: 'imi.png'
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
@keyframes floating {
  from {
    transform: translate(0, 0px);
  }
  65% {
    transform: translate(0, 10px);
  }
  to {
    transform: translate(0, -0px);
  }
}

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
  &__subheading {
    font-weight: 300;
    font-size: 1rem;
    max-width: 40ch;
    color: $grey1;
    letter-spacing: 0.02rem;
    margin: 0 0 1.5rem 0;
    strong,
    span {
      color: $dark;
    }
    @media only screen and (min-width: $lg-mobile) {
      font-size: 1.2rem;
    }
    @media only screen and (min-width: $desktop) {
      font-size: 1.4rem;
      margin: 0 0 2.5rem 0;
    }
  }
  .cta-container {
    display: flex;
    justify-content: flex-start;
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
      animation: floating 3s infinite ease-in-out;
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
  .mini-heading {
    color: $primary-color-darker;
  }
  h2 {
    z-index: 1;
    color: $primary-color-darker;
    position: relative;
  }
  background-image: linear-gradient(
      0deg,
      $primary-color-darker 20%,
      rgba(61, 64, 91, 0.8)
    ),
    url('~assets/images/sprinkle.svg');
  background-image: url('~assets/images/shiny2.svg');
  background-repeat: no-repeat, no-repeat;
  background-size: cover;
  position: relative;
  &::before {
    content: '';
    position: absolute;
    top: -8vh;
    right: 12vw;
    z-index: -1;
    background: $dark;
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

.work {
  background: $grey4;
  .mini-heading {
    color: $dark;
  }
}

.mini-heading {
  margin: 0 0 0.75rem 0.1rem;
  letter-spacing: 0.05rem;
  text-transform: uppercase;
  font-size: 0.8rem;
}

.card-list {
  padding: 0;
  list-style: none;
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  @media only screen and (min-width: $tablet) {
    margin: 2rem 0;
  }
  .card {
    flex: 1 1 250px;
    border-radius: $border-radius;
    padding: 2rem 0 1rem 0;
    @media only screen and (min-width: $tablet) {
      max-width: 40%;
    }
    .card-image {
      object-fit: cover;
      padding: 1rem 0 0.5rem 0;
      height: 20px;
      transform: scale(1);
      transition: transform 300ms cubic-bezier(0.22, 1, 0.36, 1);
      @media only screen and (min-width: $lg-mobile) {
        height: 80px;
      }
      @media only screen and (min-width: $tablet) {
        height: 120px;
      }
    }

    .card-content {
      text-align: left;
      max-width: 40ch;
      margin: 0;
      padding: 0 2rem 1rem 0;
      .card-heading {
        font-size: 1.4rem;
        color: $primary-color-darker;
        margin-bottom: 0.5rem;
        @media only screen and (min-width: $tablet) {
          margin-bottom: 1.5rem;
        }
      }
      .card-desc {
        color: #00562d;
        font-weight: 200;
        font-size: 1rem;
        line-height: 1.5;
        @media only screen and (min-width: $tablet) {
          line-height: 1.4;
          font-size: 1.2rem;
        }
      }
    }
  }
}

.logo-list {
  margin-top: 5rem;
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  padding: 0;
  justify-content: space-between;
  align-items: center;

  li > div > img {
    filter: grayscale(100%);
    width: 100%;
    max-width: 150px;
    height: auto;
    &:hover {
      transition: filter 500ms;
      filter: grayscale(0%);
    }
  }
}
</style>
