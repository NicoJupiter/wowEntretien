<template>
  <div class="intro">
    <div class="intro__logo">
      <img src="~/assets/image/WOW.png" alt="logo">
    </div>
    <div class="intro__center">
      <div class="intro__center--title">
        Extra wowrdinary
      </div>
      <div class="intro__center--subTitle">
        An almost ordinary journey - 04.23.2021
      </div>
    </div>
    <div class="intro__bottom">
      <img src="~/assets/svg/arrowDown.svg" alt="arrow">
    </div>

    <img src="~/assets/image/introImg.png" alt="intro" class="intro__img">
  </div>
</template>

<script>
export default {
  name: "Intro"
}
</script>

<style scoped lang="scss">
  .intro {
    height: 100%;
    width: 100%;
    position: relative;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    padding: 3.2rem 18.5rem 6rem;
    &__img {
      position: absolute;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      z-index: -1;
      img {
        width: 100%;
        height: 100%;
      }
    }
    &__center {
      color: $C-white;
      text-align: center;
      &--title {
        font-size: 7.2rem;
        margin-bottom: 1rem;
        font-family: $F-main;
        font-weight: bold;
      }
      &--subTitle {
        font-family: $F-main;
        font-size: 2.4rem;
      }
    }
    &__bottom {
      align-self: center;
      transform: rotate(180deg);
    }
  }
</style>
