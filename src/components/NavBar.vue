<template>
  <div class="navbar-wrapper">
    <h3>Navigacja</h3>
  </div>
</template>

<script>
export default {
  name: 'Navbar',
};
</script>

<style lang="scss" scoped>
.navbar-wrapper{
  box-shadow: 0px 0px 10px 0px #000;
  position: fixed;
  bottom: 0;
  width: 100%;
  height: 70px;
  background-color: black;
  h3{
    color:white;
    font-size: 40px;
    text-align: center;
  }
}
</style>
