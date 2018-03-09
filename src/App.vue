<template>
  <div id="app">


    <!--使用-->
    <temp></temp>
    <elementTemp></elementTemp>
    <p>
      <!--roter-link 被渲染成a标签-->
      <router-link to="/helloworld">go to hellowworld</router-link>
      <router-link to="/routertest">go to routertest</router-link>
      <router-link to="/vbindtemp">go to vbind</router-link>
      <br>
      <router-link to="/viftemp">go to vif</router-link>
    </p>
    <router-view>
      <!--路由出口 路由匹配的组件在这儿渲染-->
    </router-view>
  </div>

</template>

<script>
  import Vue from 'vue'
  import VueRouter from 'vue-router'
  //--使用组件---------------------------
  import Temp from './components/temp' //1.引入
  import ElementTemp from './components/ElementTemp'
export default {
  components: {Temp, ElementTemp}, //2.注册
  name: 'App',
//  注入路由 使用 this.$router访问
  computed: {
    username() {
      return this.$route.params.username
    }
  },
  methods: {
    goBack() {
      window.history.length > 1 ? this.$router.go(-1) : this.$router.push("/")
    }
  }
}
  //---路由------------------------------
  //  1.定义路由 两种途径
  import HelloWorld from './components/HelloWorld'
  import VbindTemp from './components/code/VbindTemp'
  import VifTemp from './components/code/VifTemp'
  const RouterTest = {template: "<div>routertest</div>"}

  //  2.定义路由
  const routes = [
    {path: "/helloworld", component: HelloWorld},
    {path: "/routertest", component: RouterTest},
    {path: "/vbindtemp", component: VbindTemp},
    {path: "/viftemp", component: VifTemp},
  ]
  //  3.创建router实例 传输rotes配置
  const router = new VueRouter({
    routes  //缩写 相当于 routes:routes
  })
  //  4.创建和挂账根实例
  const app = new Vue({
    router
  }).$mount('#app')


</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
