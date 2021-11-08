<template>
  <div class="features">
    <div class="features__title">
      Featured wowrk
    </div>
    <div class="features__list">
      <DragSlider/>
    </div>
    <div class="features__link">
     <Link :is-circle-label=false label="Discover all works" :is-white=false />
    </div>
  </div>
</template>

<script>
import DragSlider from "~/components/DragSlider";
import Link from "~/components/Link";
export default {
  name: "Features",
  components: {Link, DragSlider}
}
</script>

<style scoped lang="scss">
  .features {
    background-color: $C-white;
    padding: 12rem 0;
    box-sizing: border-box;
    width: 100%;
    height: 100%;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: center;
    @include breakpoint(xs) {
      padding: 8.6rem 0;
    }
    &__title {
      margin-bottom: 5.8rem;
      text-align: center;
      font-size: 3.2rem;
      color: $C-grey;
      font-family: $F-main;
      font-weight: $FW-bold;
      @include breakpoint(xs) {
        margin-bottom: 4rem;
      }
    }
    &__list {
      margin-bottom: 6.2rem;
      margin-left: 18.5rem;
      @include breakpoint(xs) {
        margin-left: 3.6rem;
        margin-bottom: 5.2rem;
      }
    }
    &__link {
      margin: auto;
    }
  }
</style>
