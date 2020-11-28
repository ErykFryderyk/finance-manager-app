<template>
  <div class="header">
    <div class="header__logo">
      <div class="logo">
        <img class="logo__icon" src="../assets/img/business.svg" alt="">
      </div>
    </div>
    <div class="header__welcome-user">
      <h1 class='header__title'>Witaj, Grzegorz</h1>
    </div>
  </div>
</template>

<script>

export default {
  name: 'header',
};
</script>

<style lang="scss" scoped>
.header{
  color: white;
  width: 100%;
  height: 60px;
  display: flex;
  align-items: center;
  background-color: #009688;
  box-shadow: 0px 0px 10px 10px #363636;
  &__logo{
    width: 60px;
  }

  &__title{
    font-size: 24px;
    font-weight:500;
  }
}
.logo{
  width: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2px;

  &__icon{
    fill: white;
    width: 100%;
  }
}
</style>
