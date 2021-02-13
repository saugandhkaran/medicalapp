<template>
  <nav>
    <h2 @click="goBack();">Diagnosis app</h2>
  </nav>
</template>

<script>
export default {
  name: 'TheHeader',
  methods: {
    goBack() {
      this.$router.push("/");
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
nav {
  min-height: 50px;
  max-width: 1200px;
  margin: 0 auto;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
  background-color: #5D503F;
  color: white;
  h2 {
  margin: 0;
  padding-left: 20px;
  padding-top: 8px;
  cursor: pointer;
}
}

</style>
