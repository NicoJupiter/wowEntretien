<template>
  <div class="blog">
    <div class="blog__title">
      Wlog
    </div>
    <div class="blog__center">
      <div class="blog__center__image">
        <img src="~/assets/image/blogBigImg.png" alt="">
      </div>
      <div class="blog__center__list">
        <BlogItem image-url="blogItem3.png" title="Luxury management : What…" sub-title="Jean-Noël Kapferer"/>
        <BlogItem image-url="blogItem4.png" title="The power of the blockhain" sub-title="Adrien Treccani"/>
        <BlogItem image-url="blogItem5.png" title="Social network in Europe" sub-title="Cedric Rainotte"/>
        <BlogItem image-url="blogItem6.png" title="Take action for the planet" sub-title="Bertrand Piccard"/>
        <BlogItem image-url="blogItem3.png" title="Numerical analysis in…" sub-title="Brian Solis"/>
        <BlogItem image-url="blogItem4.png" title="Build a global leader…" sub-title="Vincent Pignon"/>
      </div>
    </div>
    <div class="blog__link">
      <Link :is-circle-label=false label="Click for exclusive content" :is-white=false />
    </div>
  </div>
</template>

<script>
import BlogItem from "~/components/BlogItem";
import Link from "~/components/Link";
export default {
  name: "Blog",
  components: {Link, BlogItem}
}
</script>

<style scoped lang="scss">
  .blog {
    padding: 10rem 18.5rem;
    box-sizing: border-box;
    @include breakpoint(xs) {
      padding: 8rem 3rem;
    }
    &__title {
      margin-bottom: 6.1rem;
      font-size: 4.8rem;
      text-align: center;
      color: $C-grey;
      @include breakpoint(xs) {
        font-size: 3.6rem;
      }
    }
    &__center {
      margin-bottom: 5.4rem;
      display: flex;
      @include breakpoint(xs) {
        flex-direction: column;
      }
      &__image {
        margin-right: 5.6rem;
        @include breakpoint(xs) {
          width: 31.3rem;
          height: 31.3rem;
          margin-right: 0;
          margin-bottom: 3.1rem;
        }
        img {
          @include breakpoint(xs) {
            width: 100%;
            height: 100%;
          }
        }
      }
      &__list {
        display: flex;
        flex-wrap: wrap;

      }
    }
    &__link {
      margin: auto;
      text-align: center;
    }
  }
</style>
