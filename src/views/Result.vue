<template>
  <div class="content">
    <h1>Your result</h1>
    <div class="home">
      <div>
        <h2 class="options animate__animated animate__fadeIn">Heart issue</h2>
        <img class="options animate__animated animate__fadeIn" src="https://source.unsplash.com/Tmkwl7EjVtE/300x300" alt="heart"/>
      </div>
      <div>
        <h3 class="options animate__animated animate__fadeIn">
          Lorem Ipsum is simply dummy text of the printing and typesetting industry. 
          Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, 
          when an unknown printer took a galley of type and scrambled it to make a type specimen book. 
        </h3>
        <h3 class="options animate__animated animate__fadeIn">It has survived not only five centuries, but also the leap into electronic typesetting, 
          remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset 
          sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like 
          Aldus PageMaker including versions of Lorem Ipsum</h3>
        <button @click="goBack()" class="options animate__animated animate__fadeIn">Restart</button>
        <button class="options animate__animated animate__fadeIn">Print report</button>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Result',
  methods: {
    goBack() {
      this.$router.push('/');
    }
  }
}
</script>
<style lang="scss" scoped>
.content {
  text-align: center;
}
h1 {
  padding-top: 20px;
  margin-top: 0;
}
.content {
  min-height: 90vh;
  background-color: #F4C77E;
  border-bottom-left-radius: 6px;
  border-bottom-right-radius: 6px;
  animation: background-change 2s ease;

  h3{
    text-align: left; padding: 10px 40px;
  }
}
.home {
    display: grid;
    grid-template-columns: 4fr 8fr;
    justify-content: center;
    align-items: center;
    min-height: 60vh;
    img {
      border-radius: 6px;
    }
}

@-webkit-keyframes background-change {
  0%{background-color: #FFF0D8;}
  100%{background-color: #F4C77E;}
}

@media  screen and (max-width: 650px) {
  .home {
    display: flex;
    flex-wrap: wrap-reverse;
  }
}
</style>
