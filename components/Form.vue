<template>
  <div class="form">
    <div class="form__rowInput">
      <label class="form__row__label" for="inputName" >My name is</label>
      <input class="form__row__input" type="text" id="inputName" placeholder="type here">
      <span>,</span>
    </div>
    <div class="form__rowInput">
      <label class="form__row__label" for="inputMail" >get in touch with me at</label>
      <input class="form__row__input" type="text" id="inputMail" placeholder="your email">
    </div>
    <div class="form__rowInput">
      <label class="form__row__label" for="inputPhone" >or</label>
      <input class="form__row__input" type="text" id="inputPhone" placeholder="your phone">
    </div>
    <div class="form__row">
      <span class="form__row__label">When can we meet ?</span>
      <div class="form__row__dateList">
        <span>Asap</span>
        <span>Morning</span>
        <span class="form__row__dateList--actif">Afternoon</span>
      </div>
    </div>
    <div class="form__row">
      <span class="form__row__label">For human only, adjust the slider: 2+6=2</span>
      <div class="form__row__drag">
        <span class="form__row__drag--point"></span>
      </div>
    </div>
    <div class="form__row">
     <div class="form__row__btn">
       <img src="~/assets/svg/arrowRight.svg" alt="arrow" ref="arrowSvg">
       <span>Send</span>
     </div>
    </div>
  </div>
</template>

<script>
export default {
name: "Form"
}
</script>

<style scoped lang="scss">
  .form {
    &__row {
      margin-top: 9.4rem;
      &__label {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
        margin-right: 5rem;
      }
      &__dateList {
        display: inline-block;
        span {
          font-size: 2rem;
          color: $C-grey;
          margin-right: 2.5rem;
        }
        &--actif {
          color: $C-lightBlack !important;
          font-weight: $FW-bold;
        }
      }
      &__drag {
        margin-top: 2.8rem;
        width: 100%;
        height: .24rem;
        background-color: $C-lightBlack;
        position: relative;
        &--point {
          width: 2rem;
          height: 2rem;
          background-color: $C-lightBlack;
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%,-50%);
          border-radius: 100%;
        }
      }
      &__btn {
       font-size: 2.4rem;
        border: .24rem solid $C-lightBlack;
        padding: .8rem 3.8rem;
        display: inline-block;
        border-radius: 7rem;

        img {
          width: 3.5rem;
        }
      }
    }
    &__rowInput {
      &:not(:last-child) {
        margin-bottom: 2.75rem;
      }
      label {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
        margin-right: 1rem;
      }
      span {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
      }
      input {
        border: none;
        background-color: transparent;
        border-bottom: 1px solid $C-grey;
        width: 24rem;
        height: 3rem;
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;

        &::placeholder {
          font-size: 2.4rem;
          font-weight: $FW-bold;
          color: $C-grey;
          text-align: center;
        }
      }

    }
  }
</style>
