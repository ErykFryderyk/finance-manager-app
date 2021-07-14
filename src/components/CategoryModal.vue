<template>
  <div>
    <div class="modal-wrapper">
      <div class="modal">
        <div class="modal__btn-box">
          <button class="modal__btn modal__close-btn">X</button>
        </div>
        <div class="modal__box">
          <p>Utwórz nową kategorię:</p>
          <input type="text">
          <p>Wybierz ikonę:</p>
          <ul>
            <li>
              <input class="radio-input" type="radio" name="cars" id="mustang" checked/>
              <label class="radio-custom-label" for="mustang">
                <img src="../assets/img/home.svg" alt="Mustang"/>
              </label>
            </li>
            <li>
              <input class="radio-input" type="radio" name="cars" id="mustang"/>
              <label class="radio-custom-label" for="mustang">
                <img src="../assets/img/home.svg" alt="Mustang"/>
              </label>
            </li>
            <li>
              <input class="radio-input" type="radio" name="cars" id="mustang"/>
              <label class="radio-custom-label" for="mustang">
                <img src="../assets/img/home.svg" alt="Mustang"/>
              </label>
            </li>
          </ul>
          <div class="modal__add-btn-box">
            <button class="btn__add-budget-btn">DODAJ</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CategoryModal',
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
