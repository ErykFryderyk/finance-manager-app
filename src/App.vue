<template>
    <HeroBackground />
    <HeaderSection/>
    <MyMoney/>
    <Expenses/>
    <BudgetModal v-if="isVisibility"/>
    <CategoryModal v-if="isVisibility"/>
    <ModalAddItem v-if="isVisibility"/>
    <Navbar/>
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
  data() {
    return {
      isVisibility: false,
    };
  },
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
