<template>
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
      @check-payment="podliczWydatki"
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
      summaryTotalPrice: null,
      childrenPriceArray: [],
      items: [
        {
          icon: 'home',
          title: 'Mieszkanie',
          totalPrice: 999,
          hide: true,
          id: Math.random(),
          elems: [
            {
              id: Math.random(),
              name: 'Rachunek za prąd',
              price: 299,
            },
            {
              id: Math.random(),
              name: 'Czynsz',
              price: 700,
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
      this.checkPayment();
    },
    checkPayment() {
      this.summaryTotalPrice = 0;
      this.items.forEach((el) => {
        this.summaryTotalPrice += el.totalPrice;
      });
      this.finalSoldo = this.paymentValue - this.summaryTotalPrice;
    },
    addNewCategory(input, radio) {
      this.categoryModalVisibility = false;
      this.items.push({
        icon: radio,
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
      this.items[radioElement].elems.push({
        id: Math.random(),
        name: itemName,
        // eslint-disable-next-line radix
        price: parseInt(price),
      });
      this.podliczWydatki();
    },
    podliczWydatki() {
      let dodawana = 0;
      this.childrenPriceArray = [];
      this.items.forEach((el) => {
        el.elems.forEach((element) => {
          dodawana += element.price;
        });
        // eslint-disable-next-line radix
        this.childrenPriceArray.push(dodawana);
        dodawana = 0;
      });
      console.log(this.childrenPriceArray);
      // eslint-disable-next-line no-plusplus
      for (let i = 0; i < this.childrenPriceArray.length; i++) {
        this.items[i].totalPrice = this.childrenPriceArray[i];
      }
      this.checkPayment();
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
  background-color: #AED6F1;
  font-family: 'Poppins', sans-serif;
  height: 100vh;
}
</style>
