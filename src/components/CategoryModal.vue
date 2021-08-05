<template>
  <!-- eslint-disable max-len -->
    <div class="modal-wrapper">
      <div class="modal">
        <div class="modal__btn-box">
          <button
            class="modal__btn modal__close-btn"
            @click="$emit('close-category-modal')"
          >X</button>
        </div>
        <div class="modal__box">

          <p class="modal__text-info">Utwórz nową kategorię:</p>
          <input
            class="input-text input-text__modal"
            :class="{error: isError}"
            v-model="value"
            type="text" placeholder="Nazwa"
          >
          <p class="modal__text-info">Wybierz ikonę:</p>
          <div class="modal__list">
            <ul class="list">
              <li class="list__item">
                <input class="list__radio-input" type="radio" name="radio" id="category_1" checked/>
                <label class="custom-radio__label" for="category_1">
                  <img src="../assets/img/home.svg" alt=""/>
                </label>
              </li>
              <li class="list__item">
                <input class="list__radio-input" type="radio" name="radio" id="category_2"/>
                <label class="custom-radio__label" for="category_2">
                  <img src="../assets/img/home.svg" alt=""/>
                </label>
              </li>
              <li class="list__item">
                <input class="list__radio-input" type="radio" name="radio" id="category_3"/>
                <label class="custom-radio__label" for="category_3">
                  <img src="../assets/img/home.svg" alt=""/>
                </label>
              </li>
            </ul>
          </div>
          <div class="modal__add-btn-box">
            <button
              class="btn__add-budget-btn"
              @click="sendAction"
            >DODAJ</button>
          </div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'CategoryModal',
  data() {
    return {
      value: '',
      isError: false,
    };
  },
  methods: {
    sendAction() {
      if (this.value !== '') {
        this.$emit('add-new-category', this.value);
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
    &__list{
      display: flex;
      margin: 10px 0;
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
  .list{
    margin-top:20px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    list-style-type: none;
    margin:0;
    padding:0;
    &__item{
      list-style-type: none;

    }
    &__radio-input{
      cursor: pointer;
      display: none;
    }
  }
  .list__radio-input:checked ~ .custom-radio__label{
      border-bottom: 1px solid #000;
      box-shadow: 0px 7px 7px -7px #000;
  }
  .custom-radio{
    &__label{
      cursor:pointer;
      transition: border-bottom .5s ease, box-shadow .5s ease;
      &__label:focus{
        outline: none;
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
  img{
    width: 50px;
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
