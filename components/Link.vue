<template>
  <div class="link" ref="link">
    <img src="~/assets/svg/arrowRight.svg" alt="arrow" ref="arrowSvg" v-if="!isWhite">
    <img src="~/assets/svg/arrowRightWhite.svg" alt="arrow" ref="arrowSvg" v-if="isWhite">
    <span>{{label}}</span>
  </div>
</template>

<script>
import gsap from 'gsap'

export default {
  name: "Link",
  props: {
    isCircleLabel: {
      type: Boolean,
      required: true
    },
    label: {
      type: String,
      required: false
    },
    isWhite: {
      type: Boolean,
      required: true
    }
  },
  data() {
    return {
      mouseEnterHandler: this.mouseEnter.bind(this),
      mouseLeaveHandler: this.mouseLeave.bind(this)
    }
  },
  mounted() {
    console.log(this.$props.isCircleLabel, this.$props.isWhite)
    if (this.$props.isCircleLabel) {
      this.$refs.link.classList.add('link--circle')
    }
    if (this.$props.isWhite) {
      this.$refs.link.classList.add('link--white')
    }
    this.$refs.link.addEventListener('mouseenter', this.mouseEnterHandler)
    this.$refs.link.addEventListener('mouseleave', this.mouseLeaveHandler)
  },
  methods: {
    mouseEnter() {
      gsap.to(this.$refs.arrowSvg, {
        x: 10,
        duration: .5
      })
    },
    mouseLeave() {
      gsap.to(this.$refs.arrowSvg, {
        x: 0,
        duration: .5
      })
    }
  },
  beforeDestroy() {
    this.$refs.link.removeEventListener('mouseenter', this.mouseEnterHandler)
    this.$refs.link.removeEventListener('mouseleave', this.mouseLeaveHandler)
  }
}
</script>

<style scoped lang="scss">
  .link {
    cursor: pointer;
    color: $C-lightBlack;
    display: inline-block;
    &--circle {
      border-radius: 100%;
      border: .24rem solid $C-lightBlack;
      padding: .5rem;
    }
    &--white {
      color: $C-white;
      border: .24rem solid $C-white;
    }
    img {
      width: 3.5rem;
    }
    span {
      font-size: 2.4rem;
      color: inherit;
      font-family: $F-main;
      font-weight: $FW-bold;
    }
  }
</style>
