<template>
  <div class="citation">
    <div class="citation__text">
      Whiz kids both geeks and salesmen, your mind and hand power,
      who kick your butt and rock your world taking care of everything and anything.
    </div>
    <div class="citation__link">
      who are the wowriorrs
    </div>
    <div class="citation__img">
      <img src="~/assets/image/team.png" alt="">
    </div>
  </div>
</template>

<script>
export default {
name: "Citation"
}
</script>

<style scoped lang="scss">
  .citation {
    padding-top: 10rem;
    box-sizing: border-box;
    &__text {
      font-size: 5.6rem;
      width: 50%;
      margin-bottom: 4rem;
      margin-left:  18.5rem;
    }
    &__link {
      font-size: 2.4rem;
      margin-left:  18.5rem;
    }
    &__img {
      height: 62.2rem;
      margin-top: 12rem;
      img {
        height: 100%;
        width: 100%;
      }
    }
  }
</style>
