<template>
  <div class="features">
    <div class="features__title">
      Featured wowrk
    </div>
    <div class="features__list">
      <DragSlider/>
    </div>
    <div class="features__link">
      Discover all works
    </div>
  </div>
</template>

<script>
import DragSlider from "~/components/DragSlider";
export default {
  name: "Features",
  components: {DragSlider}
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
    &__title {
      margin-bottom: 5.8rem;
      text-align: center;
      font-size: 3.2rem;
      color: $C-grey;
      font-family: $F-main;
      font-weight: $FW-bold;
    }
    &__list {
      margin-bottom: 6.2rem;
      margin-left: 18.5rem;
    }
    &__link {
      text-align: center;
      font-size: 2.4rem;
      color: $C-black;
      font-family: $F-main;
      font-weight: $FW-bold;
    }
  }
</style>
