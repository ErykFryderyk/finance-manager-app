<template>
  <!-- eslint-disable max-len -->
  <div class="modal-wrapper">
    <div class="modal">
      <div class="modal__btn-box">
        <button
          class="modal__btn modal__close-btn"
          @click="$emit('close-add-item-modal')"
        >X</button>
      </div>
      <div class="modal__box">
        <p class="modal__text-info">Wydatki</p>
        <input
          v-model="itemName"
          :class="{error: isError}"
          autocomplete="off"
          class="input-text input-text__modal"
          type="text" placeholder="Nazwa" name="name-item">
        <input
          v-model="value"
          :class="{error: isError}"
          class="input-text input-text__modal" type="number" placeholder="Wartość" name="value-item">
        <select v-model="selectedValue" :class="{error: isError}" class="input-text input-text__modal" name="" aria-placeholder=">- brak kategori -">
          <option selected disabled>- brak kategori -</option>
          <option v-for="(item, i) in arrayCategory" :value="i" :key="item.value">
            {{item.title}}
          </option>
          <!-- <option value="2"></option> -->
          <!-- <option value="3">Dom</option> -->
        </select>
        <div class="modal__add-btn-box">
          <button
            class="btn__add-budget-btn"
            @click="checkValidation"
          >DODAJ</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalAddItem',
  props: ['arrayCategory'],
  data() {
    return {
      itemName: '',
      value: '',
      selectedValue: '',
      selectItems: this.arrayCategory,
      isError: false,
    };
  },
  methods: {
    checkValidation() {
      console.log(this.selectedValue);
      if (this.inputName !== '' && this.value !== '' && this.selectedValue !== '') {
        this.$emit(
          'add-item-to-category',
          this.itemName,
          this.value,
          this.selectedValue,
        );
        this.isError = false;
      } else {
        this.isError = true;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
  .modal-wrapper{
    background-color: rgba(0, 0, 0, 0.8);
    position: absolute;
    top:0;
    left: 0;
    bottom: 0;
    right:0;
    z-index: 999;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .modal{
    background-color:#009688;
    padding: 10px 20px 40px 20px;
    margin: 0 15px 0 15px;
    width:100%;
    max-width:400px;
    box-shadow: 0px 0px 15px 10px #00000075;
    transform: scale(0);
    animation-name: show-up;
    animation-duration: .5s;
    animation-fill-mode: forwards;
    &__btn-box{
      display: flex;
      justify-content: flex-end;
    }
    &__btn{
      width: 20px;
      height:20px;
      background-color: transparent;
      border: none;
      cursor: pointer;
      margin-bottom: 20px;
    }
    &__close-btn{
      color: #fff;
      font-size: 20px;
      padding: 5px;
      transition: color .3s ease;
      &:hover{
        color:#26313a;
      }
    }
    &__add-btn-box{
      width: 100%;
      display: flex;
      justify-content: flex-end;
    }
    &__text-info{
      font-size: 23px;
      margin-bottom: 20px;
      color: #26313a;
    }
  }
  .input-text{
    background:transparent;
    border: none;

    &__modal{
      width: 100%;
      height: 40px;
      border-bottom: 1px #016157 solid;
      margin-bottom: 20px;
      font-size: 23px;
      color: #26313a;
      padding: 0 50px 0 10px;
      outline: none;
      transition: box-shadow .3s ease;

      &:focus{
        box-shadow: 0px 10px 10px -11px #016157;
      }
      &::placeholder{
        color: #016157;
      }
    }
  }
  .btn__add-budget-btn{
    background-color: transparent;
    padding: 10px 20px;
    border: none;
    color:#26313a;
    font-size: 20px;
    border-bottom: 1px #000 solid;
    outline: none;
    transition: box-shadow .3s ease, color .3s ease;
    cursor: pointer;

    &:focus, &:hover{
      color: #000;
      box-shadow: 0px 10px 10px -11px #000;
    }
  }
  .error{
    box-shadow: 0px 10px 10px -11px orange;
    border-bottom: 1px orange solid;
    &:focus{
      box-shadow: 0px 10px 10px -11px orange;
      border-bottom: 1px orange solid;
    }
  }
  @keyframes show-up {
    0%{
      transform: scale(0);
    }
    100%{
      transform: scale(1);
    }
  }
</style>
