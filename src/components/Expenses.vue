/* eslint-disable max-len */
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
    <!-- <div class="expenses-bar expenses-bar--close">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="" xml:space="preserve">
        <path  d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/wallet.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Rachunki</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">
          Prąd<span class="expenses-box__price">200zł</span>
        </li>
        <li class="expenses-box__item">Telewizja<span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Internet<span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Telefon<span class="expenses-box__price">200zł</span></li>
      </ul>
    </div>
    <div class="expenses-bar expenses-bar--close">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/riding-car.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Samochód</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">Paliwo<span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Ubezpieczenie
          <span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Przegląd<span class="expenses-box__price">200zł</span></li>
      </ul>
    </div>
    <div class="expenses-bar expenses-bar--close">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/salad.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Jedzenie</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">Sklep Lidl<span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Biedronka<span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Pizzeria<span class="expenses-box__price">200zł</span></li>
      </ul>
    </div>
    <div class="expenses-bar expenses-bar--close">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/star.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Zachcianki</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">Bluzka Cropp
          <span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Buty Martens
          <span class="expenses-box__price">200zł</span></li>
        <li class="expenses-box__item">Zegarek Casio
          <span class="expenses-box__price">200zł</span></li>
      </ul>
    </div>
    <div class="expenses-bar expenses-bar--close">
      <div class="box-icon">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/life.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Zdrowie</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">
          Wizyta u Lekarza<span class="expenses-box__price">200zł</span>
        </li>
        <li class="expenses-box__item">
          Lekarstwa<span class="expenses-box__price">200zł</span>
        </li>
      </ul>
    </div>
    <div class="expenses-bar expenses-bar--close">
      <div class="box-icon box-icon--active">
        <svg class="box-icon__arrow" version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="451.847px" height="451.847px" viewBox="0 0 451.847 451.847" style="enable-background:new 0 0 451.847 451.847;" xml:space="preserve">
        <path d="M225.923,354.706c-8.098,0-16.195-3.092-22.369-9.263L9.27,
        151.157c-12.359-12.359-12.359-32.397,0-44.751 c12.354-12.354,
        32.388-12.354,44.748,0l171.905,171.915l171.906-171.909c12.359-12.354,
        32.391-12.354,44.744,0 c12.365,12.354,12.365,32.392,0,44.751L248.292,
        345.449C242.115,351.621,234.018,354.706,225.923,354.706z"/>
        </svg>
      </div>
      <img class="expenses-bar__icon" src="../assets/img/save-money.svg" alt="">
      <div class="expenses-bar__item">
        <h3 class="expenses-bar__title">Oszczędności</h3>
        <span class="expenses-bar__price">200,00zł</span>
      </div>
    </div>
    <div class="expenses-box expenses-box--close">
      <ul class="expenses-box__list">
        <li class="expenses-box__item">
          Wakacje<span class="expenses-box__price">200zł</span>
        </li>
        <li class="expenses-box__item">
          Nowy rower<span class="expenses-box__price">200zł</span>
        </li>
      </ul>
    </div> -->
    <button @click="getSoldo">CLick</button>
    {{soldo}}
  </div>
</template>

<script>
export default {
  name: 'Expenses',
  props: [
    'categoryName',
  ],
  data() {
    return {
      soldo: null,
      items: [
        {
          icon: '/img/home.ab898512.svg',
          title: 'Mieszkanie',
          totalPrice: 10,
          hide: true,
          id: 1,
          elems: [
            {
              id: Math.random(),
              name: 'Pierogi',
              price: 200,
            },
          ],
        },
        {
          icon: '/img/home.ab898512.svg',
          title: 'Dziewczyna',
          totalPrice: 10,
          hide: true,
          id: 2,
          elems: [
            {
              id: Math.random(),
              name: 'Saszłyk',
              price: 12,
            },
            {
              id: Math.random(),
              name: 'Kupa',
              price: 1,
            },
          ],
        },
        {
          icon: '/img/home.ab898512.svg',
          title: 'Dziewczyna',
          totalPrice: 10,
          hide: true,
          id: 3,
          elems: [
            {
              id: Math.random(),
              name: 'Kopytk',
              price: 123,
            },
          ],
        },
      ],
    };
  },
  watch: {
    categoryName(val, oldVal) {
      if (val !== oldVal) {
        this.items.push({
          id: Math.random(),
          title: val,
          icon: '/img/home.ab898512.svg',
          totalPrice: 0,
          hide: true,
          elems: [
            {
              id: Math.random(), name: 'dodany', price: 0,
            },
          ],
        });
      }
    },
  },
  methods: {
    clickEvent(id) {
      const index = this.items.findIndex((el) => el.id === id);
      this.items[index].hide = !this.items[index].hide;
    },
    createNewExpensesBar() {
      console.log(this.categoryName);
      this.items.push({
        id: Math.random(),
        name: this.categoryName,
      });
    },
    getSoldo() {
      let sum = 0;
      this.items.forEach((el) => {
        sum += el.totalPrice;
      });
      console.log(sum);
      this.soldo = sum;
      this.$emit('send-soldo', this.soldo);
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
