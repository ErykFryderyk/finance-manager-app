<template>
  <div class="header">
    <div class="header__logo">
      <div class="logo">
        <img src="../assets/img/business.svg" alt="logo-icon">
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
  background-color: #f0a167;
  box-shadow: 0px 0px 10px 1px #363636;

  &__logo{
    width: 60px;
  }
}
.logo{
  width: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 2px;

  img{
    width: 100%;
    fill: #ffffff;
  }
}

.header__title{
  font-size: 24px;
  font-weight:300;
}
</style>
