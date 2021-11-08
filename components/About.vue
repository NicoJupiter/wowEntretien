<template>
  <div class="about">
    <div class="about__title">
      What is Wow doing ?
    </div>
    <div class="about__center">
      center block
    </div>
  </div>
</template>

<script>
export default {
  name: "About"
}
</script>

<style scoped lang="scss">
  .about {
    padding: 10rem 18.5rem;
    box-sizing: border-box;
    background-color: $C-lightBlack;
    &__title {
      font-size: 3.6rem;
      margin-bottom: 5.4rem;
    }
    &__center {
      height: 49.6rem;
      background-color: pink;
    }
  }
</style>
