<template>
  <div class="clients">
    <div class="clients__title">
      Some of our clients
    </div>
    <div class="clients__list">
     <ClientList/>
    </div>
    <div class="clients__imgMobile">
      <img src="~/assets/image/mobileClient.png" alt="">
    </div>
  </div>
</template>

<script>
import ClientList from "~/components/ClientList";
export default {
  name: "Clients",
  components: {ClientList}
}
</script>

<style scoped lang="scss">
  .clients {
    padding: 12rem 18.5rem;
    box-sizing: border-box;
    background-color: $C-lighWhite;
    @include breakpoint(xs) {
      padding: 8rem 3rem;
    }
    &__title {
      font-size: 4.8rem;
      color: $C-grey;
      margin-bottom: 12rem;
      text-align: center;
      @include breakpoint(xs) {
        font-size: 3.6rem;
      }
    }
    &__list {
      height: 32rem;
      @include breakpoint(xs) {
        display: none;
      }
    }
    &__imgMobile {
      display: none;
      @include breakpoint(xs) {
        display: block;
      }
    }
  }
</style>
