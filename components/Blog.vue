<template>
  <div class="blog">
    <div class="blog__title">
      Wlog
    </div>
    <div class="blog__center"></div>
    <div class="blog__link">
      Click for exclusive contents
    </div>
  </div>
</template>

<script>
export default {
  name: "Blog"
}
</script>

<style scoped lang="scss">
  .blog {
    padding: 10rem 18.5rem;
    box-sizing: border-box;
    &__title {
      margin-bottom: 6.1rem;
      font-size: 4.8rem;
      text-align: center;
      color: $C-grey;
    }
    &__center {
      height: 24.5rem;
      background-color: pink;
      margin-bottom: 5.4rem;
    }
    &__link {
      font-size: 2.4rem;
      color: $C-black;
    }
  }
</style>
