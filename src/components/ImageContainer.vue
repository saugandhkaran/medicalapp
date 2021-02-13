<template>
  <div>
    <p v-if="!image">Image related to your answer will be shown here</p>
    <img v-if="image" alt="image" :src="image" />
  </div>
</template>

<script>
export default {
  name: 'ImageContainer',
  props: {
    image: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
p {
  text-align: center;
}
img {
  width: 300px;
  height: 300px;
  &.loading {
    background: grey;
  }
}
</style>
