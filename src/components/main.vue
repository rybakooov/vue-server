<template>
  <div id="auth-ok">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link> |
      <router-link to="/lk">Account</router-link>
      <a href="#">Log Out</a>
    </div>
    <div class="main">
      <side :user-data="userData"></side>
      <router-view/>
    </div>
  </div>
</template>

<script>
import side from '@/components/aside.vue'
import axios from 'axios'

export default {
  name: "authOk",
  data: function () {
    return {
      userData: {
        name: 'Рыбаков Александр Михайлович',
        login: 'rybakov',
        id: '1234312',
        sites: 20,
        ip: null,
      }
    }
  },
  components: {
    side
  },
  mounted() {
    axios.get('https://json.geoiplookup.io/')
    // eslint-disable-next-line no-console
      .then(result => {console.log('success:', result); this.userData.ip = result.data.ip;})
  }
}

</script>

<style scoped lang="scss">

  #nav {
    display: flex;
    align-items: center;
    padding: 20px 30px;
    border-bottom: 1px solid #e4e4e4;
  a {
    font-weight: bold;
    color: #2c3e50;
    text-decoration: none;
  &:not(:last-child){
     margin-right: 30px;
   }
  &:not(:first-child){
     margin-left: 30px;
   }
  &:last-child{
     margin-left: auto;
   }
  &.router-link-exact-active {
     color: #42b983;
   }
  }
  }
  .main{
    display: flex;
  }
</style>