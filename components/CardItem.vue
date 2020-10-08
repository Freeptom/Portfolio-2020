<template>
  <div>
    <div class="hero-container">
      <img
        :src="require(`~/assets/images/${herofile}`)"
        class="hero-container__image"
      />
    </div>
    <div class="card-content">
      <img
        :src="require(`~/assets/images/icons/${iconfile}`)"
        class="card-content__icon"
      />
      <h3>{{ heading }}</h3>
      <p>{{ desc }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    herofile: { required: true, type: String },
    iconfile: { required: true, type: String },
    heading: { required: true, type: String },
    desc: { required: true, type: String }
  }
}
</script>

<style lang="scss">
h3,
img {
  display: inline-block;
}
</style>
