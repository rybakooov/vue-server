<template>
  <div id="app">
    <auth v-if="!this.$store.state.authIsOk"></auth>
    <authOk v-else></authOk>
  </div>
</template>

<script>
import authOk from '@/components/main.vue'
import auth from '@/components/auth.vue'

export default {
  data: function(){
    return{

    }
  },
  components: {
    'authOk': authOk,
    'auth': auth
  }

}

</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
