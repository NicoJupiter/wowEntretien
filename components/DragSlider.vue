<template>
  <div class="dragSlider" ref="dragSlider">
    <div class="dragSlider__wrapper" ref="dragInner">
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider3.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider4.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider3.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider3.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider4.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider3.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider4.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider4.png" alt="">
      </div>
      <div class="dragSlider__wrapper--item">
        <img src="~/assets/image/dragSlider3.png" alt="">
      </div>
    </div>
    <div class="dragSlider__line" ref="dragIndicator">
      <span class="dragSlider__line--subLine" ref="progressBar"></span>
    </div>
  </div>
</template>

<script>
import {gsap} from "gsap";
import Hammer from '@squadette/hammerjs';

export default {
  name: "DragSlider",
  data() {
    return {
      innerX: null,
      sliderTranslate: 0,
      progressBarSetterX: null,
      innerSetterX: null,
      lastDeltaX: 0,
      limit: 0,
      dragSlidePercent: 0,
      indicatorTranslate: 0,
      limitIndicator: 0,
      stopped: false,
      progressBarX : 0,
      rafId: null,
      hammer: null,
      setupHandler: this.setup.bind(this)
    }
  },
  mounted() {
    this.setup()

    this.$data.hammer = new Hammer(this.$refs.dragInner);

    window.addEventListener('resize', this.$data.setupHandler)
    //hammer.on('panstart',this.start.bind(this))
    this.$data.hammer.on('panmove',this.move.bind(this))
    this.$data.hammer.on('panend',this.end.bind(this))

    this.play()
  },

  methods: {
    setup() {
      let el = this.$refs.dragSlider

      //pour l'opti
      this.$data.progressBarSetterX =  gsap.quickSetter(this.$refs.progressBar, "x", "px");
      this.$data.innerSetterX =  gsap.quickSetter(this.$refs.dragInner, "x", "px");

      let progressWrap = this.$refs.dragIndicator
      let progressWrapWidth = progressWrap.getBoundingClientRect().width

      // limit of the drag slider
      let visibleWidth = el.getBoundingClientRect().width
      let innerWidth = this.$refs.dragInner.getBoundingClientRect().width

      this.$data.limit = visibleWidth - innerWidth


      // update slider max value on resize
      if (this.$data.sliderTranslate  <= this.$data.limit) this.$data.sliderTranslate  = this.$data.limit

      // setup progress bar width & apply this width
      let progressBarWidth = (visibleWidth / innerWidth) * progressWrapWidth

      this.$refs.progressBar.style.width = `${progressBarWidth}px`

      // limit of the drag slider indicator
      this.$data.limitIndicator = progressWrapWidth - progressBarWidth

      //console.debug('dragSlider::bindEvents')
    },

    play() {
      this.update()
    },

    start() {
      //this.startX = e.srcEvent.pageX - this.sliderTranslate
    },
    move(e) {

      let moveX = (this.$data.lastDeltaX - e.deltaX) * 0.5

      // const x = e.srcEvent.pageX
      // const diffX = x - this.startX;

      this.$data.sliderTranslate  =  this.$data.sliderTranslate - moveX

      // stock delta pour calculer sa différence
      this.$data.lastDeltaX = e.deltaX


      if (this.$data.sliderTranslate  <= this.$data.limit) this.$data.sliderTranslate  = this.$data.limit
      if (this.$data.sliderTranslate  >= 0) this.$data.sliderTranslate  = 0

      this.$data.dragSlidePercent = (this.$data.sliderTranslate  *100) / this.$data.limit

      this.$data.indicatorTranslate =  this.$data.dragSlidePercent * this.$data.limitIndicator / 100

      /*if (this.el.opts.getSlide){
        this.debouncedHandleMove()
      }*/

    },
    end() {
      this.$data.lastDeltaX = 0
    },
    update() {
      if(!this.$data.stopped){

        const dt = 0.1;

        // moove sur le inner (la partie slidée)
        // pour éviter le changement infini a cause de la déccélération, on ajoute une fin
        if(Math.abs(this.$data.innerX - this.$data.sliderTranslate) > .5){

          this.$data.innerX += (this.$data.sliderTranslate -  this.$data.innerX) * dt;
          this.$data.innerSetterX(this.$data.innerX);
        } else {
          this.$data.innerSetterX(this.sliderTranslate);
        }

        if(Math.abs(this.$data.progressBarX - this.$data.indicatorTranslate) > .5) {
          this.$data.progressBarX += (this.$data.indicatorTranslate - this.$data.progressBarX) * dt;
          this.$data.progressBarSetterX(this.$data.progressBarX);
        } else {
          this.$data.progressBarSetterX(this.$data.indicatorTranslate);
        }

        this.$data.rafId = requestAnimationFrame(this.update.bind(this))
      }
    }
  },
  beforeDestroy() {
    cancelAnimationFrame(this.$data.rafId)
    window.removeEventListener('resize', this.$data.setupHandler)
    this.$data.hammer.off('panmove')
    this.$data.hammer.off('panend')
  }
}
</script>

<style scoped lang="scss">
  .dragSlider {
    &__wrapper {
      display: flex;
      flex-wrap: nowrap;
      margin-bottom: 2rem;
      overflow: hidden;
      min-width: -webkit-max-content;
      &--item {
        img {
          pointer-events: none;
        }
        &:not(:last-child) {
          margin-right: 2rem;
        }
      }
    }

    &__line {
      margin: auto;
      width: 20rem;
      height: .25rem;
      position: relative;
      background-color: $C-grey;
      &--subLine {
        position: absolute;
        height: .25rem;
        background-color: $C-lightBlack;
        left: 0;
        top: 0;
      }
    }

  }
</style>
