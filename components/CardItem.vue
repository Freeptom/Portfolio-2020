<template>
  <div>
    <img
      :src="require(`~/assets/images/icons/${herofile}`)"
      class="card-image"
    />
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
img {
  display: inline-block;
}
</style>
