<template>
  <div class="clients">
    <div class="clients__title">
      Some of our clients
    </div>
    <div class="clients__list">
      list
    </div>
  </div>
</template>

<script>
export default {
  name: "Clients"
}
</script>

<style scoped lang="scss">
  .clients {
    padding: 12rem 0;
    box-sizing: border-box;
    background-color: $C-lighWhite;
    &__title {
      font-size: 4.8rem;
      color: $C-grey;
      margin-bottom: 12rem;
      text-align: center;
    }
    &__list {
      height: 32rem;
      background-color: pink;
    }
  }
</style>
