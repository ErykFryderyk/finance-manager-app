<template>
  <div class="wrapper">
    <div class="previous">
      <button class="previous__btn">
        <span>&laquo;</span> Poprzedni
      </button>
    </div>
    <div class="box">
    <h2 class="box__month">Październik</h2>
    <span class="box__label">Dostępne środki</span>
    <h2 class="box__rest-money">1 000,<span>20</span> PLN</h2>
    <span class="box__label">Pensja</span>
    <h3 class="box__payment">2 130,<span>30</span> PLN</h3>
    </div>
  </div>
</template>
<script>
export default {
  name: 'my-money',
};
</script>

<style lang="scss" scoped>
.wrapper{
  background-color: #96ceb4;
  width: 100%;
  min-height: 250px;
  margin: 0 auto 0 auto;
  padding: 0 15px;
  color: #272727;
}
.previous{
  width: 100%;
  height: 50px;
  line-height: 50px;
  &__btn{
    border: none;
    background-color: transparent;
    color:#666666;
    outline:none;
    cursor: pointer;
    transition: color .3s ease;

    &:hover{
      color:red;
    }
    span{
      font-size: 18px;
    }
  }
}
.box{
  width: 100%;
  padding: 0 20px;
  &__month{
    font-size: 16px;
    font-weight:400;
    text-align:center;
    letter-spacing: 1px;
    color: #272727;
  }
  &__label{
    font-size: 14px;
    color: #272727;
  }
  &__payment{
    font-size: 22px;
    color:#26313a;
    font-weight: 500;
  }
  &__rest-money{
    font-size: 32px;
    color: #26313a;
    font-weight: 500;
  }

}
</style>
