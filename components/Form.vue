<template>
  <div class="form">
    <div class="form__rowInput">
      <label class="form__row__label" for="inputName" >My name is</label>
      <input class="form__row__input" type="text" id="inputName" placeholder="type here">
      <span>,</span>
    </div>
    <div class="form__rowInput">
      <label class="form__row__label" for="inputMail" >get in touch with me at</label>
      <input class="form__row__input" type="text" id="inputMail" placeholder="your email">
    </div>
    <div class="form__rowInput">
      <label class="form__row__label" for="inputPhone" >or</label>
      <input class="form__row__input" type="text" id="inputPhone" placeholder="your phone">
    </div>
    <div class="form__row">
      <span class="form__row__label">When can we meet ?</span>
      <div class="form__row__dateList" v-for="i in 1">
        <span ref="dateListItem">Asap</span>
        <span ref="dateListItem">Morning</span>
        <span class="form__row__dateList--actif" ref="dateListItem">Afternoon</span>
      </div>
    </div>
    <div class="form__row">
      <span class="form__row__label">For human only, adjust the slider: 2+6=2</span>
      <div class="form__row__drag">
        <span class="form__row__drag--point"></span>
      </div>
    </div>
    <div class="form__row">
     <div class="form__row__btn" ref="btn">
       <img src="~/assets/svg/arrowRight.svg" alt="arrow" ref="arrowSvg">
       <span ref="spanBtn">Send</span>
     </div>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap'
export default {
  name: "Form",
  data() {
    return {
      mouseEnterHandler: this.mouseEnter.bind(this),
      mouseLeaveHandler: this.mouseLeave.bind(this),
      mouseClickHandler: this.mouseClick.bind(this)
    }
  },
  mounted() {
    this.$refs.btn.addEventListener('mouseenter', this.$data.mouseEnterHandler)
    this.$refs.btn.addEventListener('mouseleave' ,this.$data.mouseLeaveHandler)
    this.$refs.btn.addEventListener('click' ,this.$data.mouseClickHandler)

    this.$refs.dateListItem.forEach(item => {
      let dateListClickHandler = this.dateListClick.bind(this, item)
      item.addEventListener('click', dateListClickHandler)
    })
  },
  methods: {
    dateListClick(item) {
      this.$refs.dateListItem.forEach(el => {
       el.classList.remove('form__row__dateList--actif')
      })
      item.classList.add('form__row__dateList--actif')
    },
    mouseEnter() {
      gsap.to(this.$refs.arrowSvg, {
        left: 12 + 'rem'
      })
      gsap.to(this.$refs.spanBtn, {
        left: 7 + 'rem'
      })
    },
    mouseLeave() {
      gsap.to(this.$refs.arrowSvg, {
        left: 7 + 'rem'
      })
      gsap.to(this.$refs.spanBtn, {
        left: 12 + 'rem'
      })
    },
    mouseClick() {
      console.log('click')
      gsap.to(this.$refs.btn, {
        backgroundColor: '#202124'
      })
      gsap.to(this.$refs.spanBtn, {
        color: '#F9F9F9',
        left: 50 + '%',
      })
      this.$refs.spanBtn.innerHTML = 'Send !'
      this.$refs.btn.removeEventListener('mouseenter', this.$data.mouseEnterHandler)
      this.$refs.btn.removeEventListener('mouseleave',this.$data.mouseLeaveHandler)
    }
  },
  beforeDestroy() {
    this.$refs.btn.removeEventListener('mouseenter', this.$data.mouseEnterHandler)
    this.$refs.btn.removeEventListener('mouseleave',this.$data.mouseLeaveHandler)
    this.$refs.btn.removeEventListener('click' ,this.$data.mouseClickHandler)
  }
}
</script>

<style scoped lang="scss">
  .form {
    &__row {
      margin-top: 9.4rem;
      @include breakpoint(xs) {
        &:last-child {
          text-align: center;
        }
      }
      &__label {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
        margin-right: 5rem;

      }
      &__dateList {
        display: inline-block;
        @include breakpoint(xs) {
          margin-top: 2.7rem;
        }
        span {
          font-size: 2rem;
          color: $C-grey;
          margin-right: 2.5rem;
          transition: all .5s;
        }
        &--actif {
          color: $C-lightBlack !important;
          font-weight: $FW-bold;
        }
      }
      &__drag {
        margin-top: 2.8rem;
        width: 100%;
        height: .24rem;
        background-color: $C-lightBlack;
        position: relative;
        &--point {
          width: 2rem;
          height: 2rem;
          background-color: $C-lightBlack;
          position: absolute;
          left: 50%;
          top: 50%;
          transform: translate(-50%,-50%);
          border-radius: 100%;
        }
      }
      &__btn {
       font-size: 2.4rem;
        border: .24rem solid $C-lightBlack;
        display: inline-block;
        border-radius: 7rem;
        width: 20rem;
        height: 5rem;
        position: relative;
        cursor: pointer;
        span {
          position: absolute;
          left: 12rem;
          top: 50%;
          transform: translate(-50%, -50%);
          pointer-events: none;
        }
        img {
          position: absolute;
          left: 7rem;
          top: 50%;
          transform: translate(-50%, -50%);
          width: 3.5rem;
          pointer-events: none;
        }
      }
    }
    &__rowInput {

      &:not(:last-child) {
        margin-bottom: 2.75rem;
      }
      label {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
        margin-right: 1rem;

      }
      span {
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;
      }
      input {
        border: none;
        background-color: transparent;
        border-bottom: 1px solid $C-grey;
        width: 24rem;
        height: 3rem;
        font-size: 2.4rem;
        font-weight: $FW-bold;
        color: $C-lightBlack;

        @include breakpoint(xs) {
          width: 14rem;
        }

        &::placeholder {
          font-size: 2.4rem;
          font-weight: $FW-bold;
          color: $C-grey;
          text-align: center;
        }
      }

    }
  }
</style>
