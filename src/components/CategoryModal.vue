<template>
  <div>
    <div class="modal-wrapper">
      <div class="modal">
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
        <button>DODAJ</button>
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
