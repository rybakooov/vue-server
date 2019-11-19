<template>
  <div class="home">
    <h1>Домашняя страница</h1>
    <div class="home-wrap">
      <a href="#" class="home-wrap__link">
        <img src="../assets/fm.png" alt="">
        <div class="home-wrap-desc">
          <p class="home-wrap-desc__title">Файловый менеджер</p>
        </div>
      </a>
      <a href="#" class="home-wrap__link">
        <img src="../assets/mysql.png" alt="">
        <div class="home-wrap-desc">
          <p class="home-wrap-desc__title">MySQL</p>
        </div>
      </a>
      <a href="#" class="home-wrap__link">
        <img src="../assets/sites.png" alt="">
        <div class="home-wrap-desc">
          <p class="home-wrap-desc__title">Сайты</p>
        </div>
      </a>
      <a href="#" class="home-wrap__link">
        <img src="../assets/ftp.png" alt="">
        <div class="home-wrap-desc">
          <p class="home-wrap-desc__title">FTP</p>
        </div>
      </a>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
}
</script>


<style lang="scss" scoped>
  .home{
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    flex: 1;
    &-wrap{
      display: flex;
      flex-wrap: wrap;
      box-sizing: border-box;
      &__link{
        display: flex;
        border: 1px solid #e4e4e4;
        border-radius: 10px;
        width: calc(25% - 20px);
        margin: 10px;
        box-sizing: border-box;
        text-align: center;
        text-decoration: none;
        font-weight: bold;
        color: #2c3e50;
        transition: .3s;
        padding: 10px;
        img{
          width: 50%;
        }
        &:hover{
          border-color: #42b983;
          color: #42b983;
        }
      }
      &-desc{
        box-sizing: border-box;
        padding-left: 10px;
        flex: 1;
        &__title{
        }
      }
    }
  }
</style>