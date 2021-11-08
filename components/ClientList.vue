<template>
  <div>
    <div class="clientsList" v-for="i in 1">
      <div class="clientsList__container">
        <div class="clientsList__wrapper clientsList__wrapper__right" data-direction="right" ref="wrapper">
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper"  data-direction="left" ref="wrapper">
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper clientsList__wrapper__right" data-direction="right" ref="wrapper">
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper"  data-direction="left" ref="wrapper">
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper" data-direction="left" ref="wrapper">
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper clientsList__wrapper__right"  data-direction="right" ref="wrapper">
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper" data-direction="left" ref="wrapper">
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
      <div class="clientsList__container">
        <div class="clientsList__wrapper clientsList__wrapper__right"  data-direction="right" ref="wrapper">
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
          <div class="clientsList__wrapper__item">
            <img src="~/assets/image/clientListItem1.png" alt="">
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import gsap from 'gsap'
export default {
  name: "ClientList",
  mounted() {
    this.$refs.wrapper.forEach(item => {
      if(item.dataset.direction === 'left') {
        gsap.to(item.children, {
          xPercent: -100,
          duration: 1,
          repeat: -1,
          repeatDelay: 2
        })
      } else if (item.dataset.direction === 'right') {
        gsap.to(item.children, {
          xPercent: 100,
          duration: 1,
          repeat: -1,
          repeatDelay: 2
        })
      }
    })
  }
}
</script>

<style scoped lang="scss">
  .clientsList {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    height: 100%;
    &__container {
      width: 25%;
      display: flex;
      justify-content: center;
    }
    &__wrapper {
      display: flex;
      width: 16.2rem;
      overflow: hidden;
      &:not(:last-child) {
        margin-right: 4rem;
      }
      &__right {
        div {
          transform: translateX(-100%);
        }
      }

    }
  }
</style>
