<template>
  <div class="homepage">
    <div class="homepage__1">
      <Intro/>
    </div>
  </div>
</template>

<script>
import Intro from "~/components/Intro";
export default {
  components: {Intro}
}
</script>

<style lang="scss" scoped>
  .homepage {
    &__1 {
      width: 100vw;
      height: 100vh;
      overflow: hidden;
    }
  }
</style>
