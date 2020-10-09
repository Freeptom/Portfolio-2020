<template>
  <div>
    <div class="hero-container">
      <img
        :src="require(`~/assets/images/icons/${herofile}`)"
        class="hero-container__image"
      />
    </div>
    <div class="card-content">
      <h3 class="card-heading">{{ heading }}</h3>
      <p class="card-desc">{{ desc }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    herofile: { required: true, type: String },
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
