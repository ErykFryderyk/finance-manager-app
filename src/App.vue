<template>
  <Background />
  <div class="container">
    <h1>Hello World</h1>
  </div>
</template>

<script>
import HeroBackground from './components/HeroBackground.vue';

export default {
  name: 'App',
  data() {
    return {
      title: 'Hello Grzegorz',
    };
  },
  components: {
    Background: HeroBackground,
  },
};
</script>

<style
    HeroBackground lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body{
  font-size: 17px;
  // background-color: black;
  color: white;
}
.container{
  width: 100%;
  height: 100vh;
  margin: 0 auto 0 auto;
  padding: 0 15px 0 15px;
}

</style>
