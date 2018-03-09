<template>
  <div id="vbind">
    <span v-bind:title="message">
      鼠标悬停查看此处绑定信息 v-bind:title
    </span>
  </div>
</template>

<script>
  export default {
    name: "vbind-temp.vue",
    data() {
      return {
        message: "v-bind:title message"
      }
    }
  }

</script>

<style scoped>

</style>
