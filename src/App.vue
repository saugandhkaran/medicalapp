<template>
  <div id="app">
    <TheHeader />
    <div class="content">
      <router-view/>
    </div>
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css"
    />
  </div>
</template>
<script>
import TheHeader from '@/components/TheHeader';
export default {
  name: 'Home',
  components: {
    TheHeader
  }
}
</script>
<style lang="scss">
body {
  background-color: #e5e1db;
background-image: url("data:image/svg+xml,%3Csvg width='32' height='64' viewBox='0 0 32 64' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M0 28h20V16h-4v8H4V4h28v28h-4V8H8v12h4v-8h12v20H0v-4zm12 8h20v4H16v24H0v-4h12V36zm16 12h-4v12h8v4H20V44h12v12h-4v-8zM0 36h8v20H0v-4h4V40H0v-4z' fill='%23cecece' fill-opacity='0.4' fill-rule='evenodd'/%3E%3C/svg%3E");
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #5D503F;
}

.content {
  max-width: 1200px;
  margin: 0 auto;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}

button {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  background-color: #F6A116;
  color: white;
  font-size: 16px;
  border: none;
  padding: 10px 15px;
  border-radius: 25px;
  margin: 10px;
  font-weight: bold;
  cursor: pointer;
}
</style>
