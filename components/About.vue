<template>
  <div class="about">
    <div class="about__title">
      What is Wow doing ?
    </div>
    <div class="about__center" v-for="i in 1">
      <AboutItem ref="aboutItem" image-url="aboutImg.png" content="With more of 150 projects from the beginning.
        Wow can help you to develop a strategy
        and expand it during all of our collaboration."/>

      <AboutItem ref="aboutItem" image-url="aboutImg2.png" content="From design to
       websites, not to mention videos, photographs and so on,
      Wow is the perfect company to create all the design of your brand and decline it everywhere."/>

      <AboutItem ref="aboutItem" image-url="aboutImg3.png" content="Care deeply about your web presence ?
      Wow have professionals in different fields
      relative to web to create you a website, fully adapted to you and your needs."/>

      <AboutItem ref="aboutItem" image-url="aboutImg4.png" content="Your brand is on social medias ?
      Wow accompany you on Facebook,
       LinkedIn, Instagram, TikTok to attract people to your brand."/>
    </div>
  </div>
</template>

<script>
import AboutItem from "~/components/AboutItem";
import gsap from 'gsap'
export default {
  name: "About",
  components: {AboutItem},
  mounted() {
    gsap.set(this.$refs.aboutItem[0].$el, {
      opacity: 1,
      zIndex: 1
    })
    gsap.set(this.$refs.aboutItem[0].$refs.aboutItemLink[0], {
      opacity: 1,
    })
    this.$nuxt.$on('aboutItem::click', (i) => {
      let tl = gsap.timeline()
      this.$refs.aboutItem.forEach(item => {
        tl.to(item.$el, {
          opacity: 0,
          zIndex: 0,
          duration: .5
        }, 0)
      })

      tl.to(this.$refs.aboutItem[i].$el, {
        opacity: 1,
        zIndex: 1,
        duration: .5,
      }, .5)
      tl.to(this.$refs.aboutItem[i].$refs.aboutItemLink[i], {
        opacity: 1,
        duration: .1,
      }, .5)
    })
  },
  beforeDestroy() {
    this.$nuxt.$off('aboutItem::click')
  }
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
      color: $C-white;
    }
    &__center {
      height: 49.6rem;
      position: relative;
    }
  }

</style>
