<template>
  <div class="blogItem">
    <div class="blogItem__image">
      <img :src="require(`~/assets/image/${imageUrl}`)" alt="">
    </div>
    <div class="blogItem__content">
      <div class="blogItem__content__title">
        {{title}}
      </div>
      <div class="blogItem__content__subTitle">
        {{subTitle}}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BlogItem",
  props: {
    imageUrl: {
      type:String,
      required: true
    },
    title: {
      type:String,
      required: true
    },
    subTitle: {
      type:String,
      required: true
    }
  },
}
</script>

<style scoped lang="scss">
  .blogItem {
    display: flex;
    align-items: center;
    flex: 50%;
    @include breakpoint(xs) {
      flex: 100%;
      &:not(:last-child) {
        margin-bottom: 1rem;
      }
      &:nth-child(3),
      &:nth-child(4),
      &:nth-child(5),{
        display: none;
      }

    }
    &__content {
      margin-left: 2rem;
      &__title {
        font-size: 1.8rem;
        color: $C-lightBlack;
        margin-bottom: .5rem;
      }
      &__subTitle {
        font-size: 1.4rem;
        color: $C-grey;
      }
    }
  }
</style>
