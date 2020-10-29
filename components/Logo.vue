<template>
  <div>
    <img :src="require(`~/assets/images/logos/${logo}`)" />
  </div>
</template>

<script>
export default {
  props: {
    logo: { required: true, type: String }
  }
}
</script>

<style lang="scss">
img {
  display: inline-block;
}
</style>
