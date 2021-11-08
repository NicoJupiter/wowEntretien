<template>
  <div class="contact">
    <div class="contact__title">
      you are extraWowrdinary
    </div>
    <div class="contact__center">
      <div class="contact__center__text">
        Get in touch
      </div>
      <div class="contact__center__form">
        <Form/>
      </div>
    </div>
  </div>
</template>

<script>
import Form from "~/components/Form";
export default {
name: "Contact",
  components: {Form}
}
</script>

<style scoped lang="scss">
  .contact {
    background-color: $C-lighWhite;
    width: 100%;
    height: 100%;
    padding: 12rem 18.5rem;
    @include breakpoint(xs) {
      padding: 10rem 2rem;
    }
    &__title {
      color: $C-lightBlack;
      font-size: 5.6rem;
      text-align: center;
      font-family: $F-main;
      font-weight: $FW-bold;
      margin-bottom: 10.9rem;
      @include breakpoint(xs) {
        font-size: 3.6rem;
      }
    }
    &__center {
      display: flex;
      @include breakpoint(xs) {
        flex-direction: column;
      }
      &__text {
        font-size: 5.6rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
        margin-right: 10.8rem;
        @include breakpoint(xs) {
          font-size: 3.6rem;
          margin-right: 0;
          text-align: center;
          margin-bottom: 4rem;
        }
      }
      &__form {

      }
    }
  }
</style>
