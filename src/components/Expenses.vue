<template>
  <div
    class="expenses-wrapper"
    v-for="item in items"
    :key="item.id">
    <div class="expenses-bar"
      :class="{ active: item.hide}"
      @click="clickEvent(item.id)">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" :src="item.icon" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">{{ item.title }}</h3>
        <span class="expenses-bar__price">{{ item.totalPrice }} zł</span>
      </div>
    </div>
    <div class="expenses-box"
      :class="{hide: item.hide}">
      <ul class="expenses-box__list">
        <li
          class="expenses-box__item"
          v-for="el in item.elems" :key="el.id">
          {{ el.name }}
          <span class="expenses-box__price">
            {{ el.price }} zł
          </span>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Expenses',
  props: [
    'items',
  ],
  data() {
    return {
      soldo: null,
    };
  },
  watch: {
    // categoryName(val, oldVal) {
    //   if (val !== oldVal) {
    //     this.items.push({
    //       id: Math.random(),
    //       title: val,
    //       icon: '/img/home.ab898512.svg',
    //       totalPrice: 0,
    //       hide: true,
    //       elems: [
    //         // {
    //         //   id: Math.random(), name: 'dodany', price: 10,
    //         // },
    //       ],
    //     });
    //   }
    // },
  },
  methods: {
    clickEvent(id) {
      const index = this.items.findIndex((el) => id === el.id);
      console.log(index);
      console.log(this.items[1]);
      // eslint-disable-next-line vue/no-mutating-props
      this.items[index].hide = !this.items[index].hide;
    },
    createNewExpensesBar() {
      console.log(this.categoryName);
      // eslint-disable-next-line vue/no-mutating-props
      this.items.push({
        id: Math.random(),
        name: this.categoryName,
      });
    },
  },
};
</script>

<style lang="scss" scoped>
.expenses-wrapper{
  width: 100%;
  border-bottom: 1px solid #0000001f;
}
.expenses-bar{
  display: flex;
  align-items: center;
  height: 50px;
  cursor:pointer;
  border-bottom: 1px solid #0000001f;
  transition: background-color .3s ease;

  &__icon{
    width: 30px;
    height: 30px;
    margin: 0px 5px;
  }
  &__item{
    width: 100%;
    display: flex;
    justify-content: space-between;
    margin: 0px 10px;
  }
  &__title{
    font-size: 19px;
    font-weight: 400;
    color: #303030;
  }
  &__price{
    font-size: 16px;
    font-weight: 600;
    color:#303030;
  }
  &--active{
    .box-icon{
      transform: rotate(-90deg);
    }
  }
  &:hover{
    background-color: #fff;
  }
}
.box-icon{
  width: 10px;
  height: 10px;
  display:flex;
  justify-content: center;
  align-items: center;
  margin: 0 10px;
  fill:  #00000040;
  transition: transform .3s ease;
}
.active .box-icon{
    transform: rotate(-90deg);
}
.expenses-box{
  width: 100%;
  background-color: #00000040;;
  transition: transform 0.3s ease;

  &__list{
    list-style: none;
    padding: 5px 0;
    margin:0 30px;
  }

  &__item{
    display: flex;
    justify-content: space-between;
  }

  &--close{
    height: 0;
    display: none;
    transform: scaleY(0) translateY(-100%);
  }
}
.hide{
  display:none;
}
</style>
