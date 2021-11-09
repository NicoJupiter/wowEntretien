<template>
  <div class="homepage">
    <div class="homepage__1">
      <Intro/>
    </div>
    <div class="homepage__2">
      <Features/>
    </div>
    <div class="homepage__3">
      <About/>
    </div>
    <div class="homepage__4">
      <Blog/>
    </div>
    <div class="homepage__5">
      <Clients/>
    </div>
    <div class="homepage__6">
      <Citation/>
    </div>
    <div class="homepage__7">
      <Contact/>
    </div>
  </div>
</template>

<script>
import Intro from "~/components/Intro";
import Features from "~/components/Features";
import About from "~/components/About";
import Blog from "~/components/Blog";
import Clients from "~/components/Clients";
import Citation from "~/components/Citation";
import Contact from "~/components/Contact";
export default {
  components: {Contact, Citation, Clients, Blog, About, Features, Intro}
}
</script>

<style lang="scss" scoped>
  .homepage {
    overflow: hidden;
    &__1,
    &__2
    {
      width: 100vw;
      height: 100vh;
      overflow: hidden;
    }
    &__2,
    &__7{
      @include breakpoint(xs) {
        height: auto;
      }
    }
  }
</style>
