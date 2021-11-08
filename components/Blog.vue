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
      Click for exclusive contents
    </div>
  </div>
</template>

<script>
import BlogItem from "~/components/BlogItem";
export default {
  name: "Blog",
  components: {BlogItem}
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
      margin-bottom: 5.4rem;
      display: flex;
      &__image {
        margin-right: 5.6rem;
      }
      &__list {
        display: flex;
        flex-wrap: wrap;

      }
    }
    &__link {
      font-size: 2.4rem;
      color: $C-black;
      text-align: center;
    }
  }
</style>
