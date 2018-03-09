<template>
  <div id="vIfTemp">
    <p v-if="seen">v if test</p>
  </div>
</template>

<script>
  export default {
    name: "vif-temp",
    data() {
      return {
        seen: true
      }
    }
  }
</script>

<style scoped>

</style>
