<template>
    <Background />
    <Header/>
    <Money/>
    <ExpensesSection/>
    <NavbarSection/>
</template>

<script>
import HeroBackground from './components/HeroBackground.vue';
import HeaderSection from './components/Header.vue';
import MyMoney from './components/MyMoney.vue';
import Expenses from './components/Expenses.vue';
import Navbar from './components/NavBar.vue';

export default {
  name: 'App',
  data() {
    return {
      title: 'Hello Grzegorz',
    };
  },
  components: {
    Background: HeroBackground,
    Header: HeaderSection,
    Money: MyMoney,
    ExpensesSection: Expenses,
    NavbarSection: Navbar,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;700&display=swap');
*{
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
