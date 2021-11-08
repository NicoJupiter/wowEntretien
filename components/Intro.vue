<template>
  <div class="intro">
    <div class="intro__logo">
      <img src="~/assets/image/WOW.png" alt="logo">
      <img class="intro__logo--mobileIcon" src="~/assets/image/mobileMenu.png" alt="logo">
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
      <Link :is-white=true label="" :is-circle-label=true />
    </div>

  </div>
</template>

<script>
import Link from "~/components/Link";
import imgBackground from '@/assets/image/introImg.png'
export default {
  name: "Intro",
  components: {Link}
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
    background-image:  url('~assets/image/introImg.png');
    background-size: cover;
    background-position: center;
    @include breakpoint(xs) {
      padding: 2.5rem 3.6rem 3.4rem;
    }
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

    &__logo {
      display: flex;
      justify-content: space-between;
      align-items: center;
      &--mobileIcon {
        display: none;
        height: 1.5rem;
        @include breakpoint(xs) {
          display: block;
        }
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
        @include breakpoint(xs) {
          font-size: 3.6rem;
        }
      }
      &--subTitle {
        font-family: $F-main;
        font-size: 2.4rem;
        @include breakpoint(xs) {
          font-size: 2rem;
        }
      }
    }
    &__bottom {
      align-self: center;
      transform: rotate(90deg);

    }
  }
</style>
