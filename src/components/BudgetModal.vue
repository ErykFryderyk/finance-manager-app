<template>
  <div class="modal-wrapper">
    <div class="modal">
      <div class="modal__btn-box">
        <button
          @click="$emit('close-modal')"
          class="modal__btn modal__close-btn">X</button>
      </div>
      <div class="modal__box">
        <p class="modal__text-info">Twoja miesięczna wypłata</p>
        <input
          v-model="value"
          class="input-text input-text__modal"
          :class="{ error: isError}"
          type="number"
          placeholder="Wprowadź wartość"
        >
        <div class="modal__add-btn-box">
          <button
            @click="actionModal"
            class="btn__add-budget-btn">
              DODAJ
            </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'BudgetModal',
  data() {
    return {
      value: '',
      isError: false,
    };
  },
  methods: {
    actionModal() {
      if (this.value !== '') {
        this.$emit('close-modal', this.value);
        this.value = '';
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
  .modal{
    background-color:#009688;
    padding: 10px 20px 40px 20px;
    box-shadow: 0px 0px 15px 10px #00000075;
    transform: scale(0);
    animation-name: show-up;
    animation-duration: .3s;
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
    &__box{
      display: flex;
      align-items:center;
      justify-content: center;
      flex-direction: column;
    }
    &__text-info{
      font-size: 23px;
      margin-bottom: 20px;
      color: #26313a;
    }
    &__add-btn-box{
      width: 100%;
      display: flex;
      justify-content: flex-end;
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
        border-bottom: 1px #016157 solid;

      }
      &::placeholder{
        color: #016157;
        font-size: 19px;
      }
    }
  }
  .error {
    box-shadow: 0px 10px 10px -11px orange;
    border-bottom: 1px orange solid;
    &:focus{
      box-shadow: 0px 10px 10px -11px orange;
      border-bottom: 1px orange solid;
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
  @keyframes show-up {
    0%{
      transform: scale(0);
    }
    100%{
      transform: scale(1);
    }
  }
</style>
