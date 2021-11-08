<template>
  <div class="aboutItem">
    <div class="aboutItem__image">
      <img :src="require(`~/assets/image/${imageUrl}`)" alt="">
    </div>
    <div class="aboutItem__content">
      <div class="aboutItem__content__list" v-for="i in 1">
        <div class="aboutItem__content__list__item" ref="aboutItemLink" data-index="0">
         Strategy & Consulting
        </div>
        <div class="aboutItem__content__list__item" ref="aboutItemLink" data-index="1">
          Design & production
        </div>
        <div class="aboutItem__content__list__item" ref="aboutItemLink" data-index="2">
          Technology & innovation
        </div>
        <div class="aboutItem__content__list__item" ref="aboutItemLink" data-index="3">
          Advertising & data
        </div>
      </div>
      <div class="aboutItem__content__text">
        {{content}}
      </div>
      <div class="aboutItem__content__link">
        <Link :is-circle-label=true label="" :is-white=true />
        <span>Let's meet</span>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap'
import Link from "~/components/Link";

export default {
  name: "AboutItem",
  components: {Link},
  props: {
    imageUrl: {
      type:String,
      required: true
    },
    content: {
      type:String,
      required: true
    }
  },
  data() {
    return {

    }
  },
  mounted() {

    this.$refs.aboutItemLink.forEach(item => {
      let clickEventHandler =  this.clickEvent.bind(this, item)
      item.addEventListener('click', clickEventHandler)
    })
  },
  methods: {
    clickEvent(item) {
      this.$nuxt.$emit('aboutItem::click', item.dataset.index)
      /*this.$refs.aboutItemLink.forEach(item => {
        gsap.to(item, {
          opacity: .5,
          duration: .5
        })
      })
      gsap.to(this.$refs.aboutItemLink[item.dataset.index], {
        opacity: 1,
        duration: .5
      })*/
    }
  },
  beforeDestroy() {
    this.$refs.aboutItemLink.forEach(item => {
      let clickEventHandler =  this.clickEvent.bind(this, item)
      item.removeEventListener('click', clickEventHandler)
    })
  }
}
</script>

<style scoped lang="scss">
.aboutItem {
  opacity: 0;
  position: absolute;
  left: 0;
  top: 0;
  width: 100%;
  height: 100%;
  display: flex;
  &__image {
    width: 40.9rem;
    height: 32.6rem;
    margin-top: 4.6rem;
    margin-right: 1.6rem;
  }
  &__content {
    &__list {
      margin-left: 2.7rem;
      margin-bottom: 3.1rem;
      display: flex;
      &__item {
        font-size: 2rem;
        color: $C-white;
        opacity: .5;

        font-family: $F-main;
        &:not(:last-child) {
          margin-right: 6rem;
        }
        &:hover {
          opacity: 1;
        }
      }
    }
    &__text {
      font-size: 2.4rem;
      color: $C-white;
      margin-bottom: 3.2rem;
      width: 80%;
      font-family: $F-main;
      font-weight: $FW-bold;
    }
    &__link {
      span {
        font-size: 2.4rem;
        color: $C-white;
        font-family: $F-main;
        font-weight: $FW-bold;
        margin-left: 1rem;
      }
    }
  }
}
</style>
