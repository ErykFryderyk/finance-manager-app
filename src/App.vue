<template>
  <Header/>
  <Background />
  <Input />
</template>

<script>
import HeaderSection from './components/Header.vue';
import HeroBackground from './components/HeroBackground.vue';
import SearchInput from './components/SearchInput.vue';

export default {
  name: 'App',
  data() {
    return {
      title: 'Hello Grzegorz',
    };
  },
  components: {
    Header: HeaderSection,
    Background: HeroBackground,
    Input: SearchInput,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;700&display=swap');
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body{
  font-size: 17px;
  // background-color: black;
  color: black;
  font-family: 'Poppins', sans-serif;
}
.container{
  width: 100%;
  height: 100vh;
  margin: 0 auto 0 auto;
  padding: 0 15px 0 15px;
}

</style>
