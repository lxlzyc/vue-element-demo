<template>
  <div id="temp">
    <h1>temp component </h1>
    <a> --> {{tempcontent}}) </a>
  </div>
</template>

<script>
  export default {
    name: "temp",
    data() {
      return {
        tempcontent: "temp content 233" //组件中这样赋值
      }
    }
  }
  // var vm = new Vue({      组件无法调用Vue
  //   el:"#tempcomponent",
  //   data:{
  //     message:"hello tempcontent"
  //   }
  // })
</script>

<style scoped>

</style>
