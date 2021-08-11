/* eslint-disable vue/script-setup-uses-vars */
<template>
    <HeroBackground />
    <HeaderSection/>
    <MyMoney
      :payment="paymentValue"
      :soldo="finalSoldo"
    />
    <Expenses
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
      :arrayCategory="elItems"
      v-if="addItemModalVisibility"
      @close-add-item-modal="addItemModalVisibility = false"
      @add-new-item="showValue"
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
      finalSoldo: 200,
      paymentValue: 2001,
      categoryName: '',
      budgetModalVisibility: false,
      categoryModalVisibility: false,
      addItemModalVisibility: false,
      elItems: [],
    };
  },
  methods: {
    showModal(value) {
      if (value !== undefined) {
        this.paymentValue = value;
      }
      this.budgetModalVisibility = !this.budgetModalVisibility;
    },
    addNewCategory(value) {
      this.categoryName = value;
      this.categoryModalVisibility = false;
    },
    updateSoldo(value) {
      this.finalSoldo = value;
    },
    addArrayInside(arrayFromExpanses) {
      this.elItems = arrayFromExpanses;
      console.log(this.elItems);
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
