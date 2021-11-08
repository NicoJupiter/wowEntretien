<template>
  <div class="citation">
    <div class="citation__text">
      Whiz kids both geeks and salesmen, your mind and hand power,
      who kick your butt and rock your world taking care of everything and anything.
    </div>
    <div class="citation__link">
      <Link :is-circle-label=true label="" :is-white=false />
      <span>who are the wowriorrs</span>
    </div>
    <div class="citation__img">
      <img src="~/assets/image/team.png" alt="">
    </div>
  </div>
</template>

<script>
import Link from "~/components/Link";
export default {
name: "Citation",
  components: {Link}
}
</script>

<style scoped lang="scss">
  .citation {
    padding-top: 10rem;
    box-sizing: border-box;
    @include breakpoint(xs) {
      padding-top: 1rem;
    }
    &__text {
      font-size: 5.6rem;
      width: 50%;
      margin-bottom: 4rem;
      margin-left:  18.5rem;
      font-family: $F-main;
      font-weight: bold;
      color: $C-lightBlack;
      @include breakpoint(xs) {
        font-size: 4.6rem;
        width: 100%;
        margin-left: 0;

        padding-left: 3rem;
        padding-right: 3rem;
      }
    }
    &__link {
      font-size: 2.4rem;
      margin-left:  18.5rem;
      font-family: $F-main;
      font-weight: bold;
      color: $C-lightBlack;
      span {
        margin-left: 1rem;
      }
      @include breakpoint(xs) {
        margin-left: 0;
        padding-left: 3rem;
        padding-right: 3rem;
      }
    }
    &__img {
      height: 62.2rem;
      margin-top: 12rem;
      @include breakpoint(xs) {
        height: 25rem;
      }
      img {
        height: 100%;
        width: 100%;
      }
    }
  }
</style>
