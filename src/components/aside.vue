<template>
  <aside class="aside">
    <p class="aside__title">Имя пользователя:</p>
    <div class="aside__text">{{ userData.name }}</div>
    <p class="aside__title">Логин:</p>
    <div class="aside__text">{{ userData.login }}</div>
    <p class="aside__title">ID пользователя:</p>
    <div class="aside__text">{{ userData.id }}</div>
    <p class="aside__title">Количество сайтов:</p>
    <div class="aside__text">{{ userData.sites }}</div>
    <p class="aside__title">IP:</p>
    <div class="aside__text">{{ userData.ip }}</div>
  </aside>
</template>

<script>
  export default {
    name: "side",
    props: {
      userData: Object
    }
  }
</script>

<style scoped lang="scss">
  .aside{
    height: calc(100vh - 60px);
    border-right: 1px solid #e4e4e4;
    padding: 30px;
    box-sizing: border-box;
    &__title{
      font-weight: bold;
      text-align: left;
      font-size: 18px;
      margin-bottom: 10px;
      &:not(:first-child){
        margin-top: 40px;
      }
    }
    &__text{
      font-size: 16px;
      text-align: left;
    }
  }
</style>