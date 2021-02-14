<template>
  <nav>
    <h2 @click="goBack();">Diagnosis app</h2>
    <div class="flex-container">
      <h3>Categories</h3>
      <h3>Login</h3>
    </div>
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
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin: 0 auto;
  border-top-left-radius: 6px;
  border-top-right-radius: 6px;
  background-color: #5D503F;
  color: white;
  div {
    padding-right: 20px;
  }
  h2, h3 {
    cursor: pointer;
    margin: 0;
    padding-left: 20px;
    cursor: pointer;
  }
}

</style>
