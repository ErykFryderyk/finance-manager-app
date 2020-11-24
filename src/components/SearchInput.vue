<template>
  <div class="search-box">
    <input class="search" type="text" placeholder="Wpisz imię...">
  </div>
</template>

<script>
export default {
  name: 'SearchInput',
};
</script>

<style lang="scss" scoped>
.search-box{
  width: 100%;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.search{
  width: 200px;
  height: 50px;
  background-color: #909090;
}
</style>
