<template>
<div class="">
  <div class="hero-background"/>
</div>
</template>

<script>
export default {
  name: 'HeroBackground',
};
</script>

<style lang="scss" scoped>
.hero-background{
  width: 100%;
  height: 100vh;
  position: fixed;
  background-color: red;
  z-index: -1;
}
</style>
