<template>
  <div class="modal-wrapper">
    <div class="modal">
      <p>Wydatki</p>
      <input type="text" placeholder="Nazwa" name="name-item">
      <input type="number" placeholder="Wartość" name="value-item">
      <select name="" id="">
        <option value="">- brak kategori -</option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalAddItem',
};
</script>

<style lang="scss" scoped>
  .modal-wrapper{
    background-color: rgba(0, 0, 0, 0.8);
    position: fixed;
    top:0;
    left: 0;
    bottom: 0;
    right:0;
    z-index: 999;
    display: flex;
    justify-content: center;
    align-items: center;
  }
</style>
