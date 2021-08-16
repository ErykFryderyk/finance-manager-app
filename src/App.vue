<template>
    <HeroBackground />
    <HeaderSection/>
    <MyMoney
      :payment="paymentValue"
      :soldo="finalSoldo"
    />
    <Expenses
      :items="items" v-model="items"
      :categoryName="categoryName"
      @send-soldo="updateSoldo"
      @category-out="addArrayInside"
    />
    <BudgetModal
      @close-modal="showModal"
      v-if="budgetModalVisibility"
    />
    <CategoryModal
      @close-category-modal="categoryModalVisibility = false"
      @add-new-category="addNewCategory"
      v-if="categoryModalVisibility"
    />
    <ModalAddItem
      :arrayCategory="items"
      v-if="addItemModalVisibility"
      @close-add-item-modal="addItemModalVisibility = false"
      @add-item-to-category="showValues"
      @show="info"
    />
    <Navbar
      @budget-open="budgetModalVisibility = true"
      @category-open="categoryModalVisibility = true "
      @add-item-open="addItemModalVisibility = true"
    />
</template>

<script>
import HeroBackground from './components/HeroBackground.vue';
import HeaderSection from './components/Header.vue';
import MyMoney from './components/MyMoney.vue';
import Expenses from './components/Expenses.vue';
import Navbar from './components/NavBar.vue';
import BudgetModal from './components/BudgetModal.vue';
import CategoryModal from './components/CategoryModal.vue';
import ModalAddItem from './components/ModalAddItem.vue';

export default {
  name: 'App',
  components: {
    HeroBackground,
    HeaderSection,
    MyMoney,
    Expenses,
    Navbar,
    BudgetModal,
    CategoryModal,
    ModalAddItem,
  },
  data() {
    return {
      finalSoldo: 0,
      paymentValue: 0,
      categoryName: '',
      budgetModalVisibility: false,
      categoryModalVisibility: false,
      addItemModalVisibility: false,
      elItems: [],
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
              price: 20,
            },
          ],
        },
        {
          icon: '/img/home.ab898512.svg',
          title: 'Dom',
          totalPrice: 10,
          hide: true,
          id: 2,
          elems: [
            {
              id: Math.random(),
              name: 'Owca',
              price: 3,
            },
          ],
        },
      ],
    };
  },
  methods: {
    showModal(value) {
      if (value !== undefined) {
        this.paymentValue = value;
      }
      this.budgetModalVisibility = !this.budgetModalVisibility;
    },
    addNewCategory(input, radio) {
      this.categoryModalVisibility = false;
      this.items.push({
        icon: `/img/${radio}.ab898512.svg`,
        title: input,
        totalPrice: 0,
        hide: true,
        id: Math.random(),
        elems: [],
      });
    },
    updateSoldo(value) {
      this.finalSoldo = value;
    },
    addArrayInside(arrayFromExpanses) {
      this.elItems = arrayFromExpanses;
      console.log(this.elItems);
    },
    showValues(itemName, price, radioElement) {
      this.addItemModalVisibility = !this.addItemModalVisibility;
      this.items[radioElement].elems.push({ id: Math.random(), name: itemName, price });
    },
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;700&display=swap');
*, *::before, *::after{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body{
  font-size: 17px;
  color: black;
  font-family: 'Poppins', sans-serif;
}
</style>
