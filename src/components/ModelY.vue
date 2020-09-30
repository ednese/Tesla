<template>
    <div class="Y">
        <h1 class="ModelY__title">Model Y</h1>
        <p class="ModelY__subtitle">Order Online for <a class="ModelY__subtitle__desc underline" href="#">Touchless Delivery</a></p>
        <img class="ModelY__background" src="../img/Desktop-ModelY.jpg"/>
    </div>
</template>

<script>
import '@/style/nav.css'
export default {
  name: 'Nav',
  data () {
    return {
      count: 0
    }
  },
  methods: {
    add: function () {
      this.count++
    }
  }
}
</script>

<style scoped>
    .ModelY__background {
        position: absolute;
        left: 0px;right: 0px;bottom: 0px;top: 0px;
        width: 100vw;
        min-width: 1130px;
        z-index: -1;
}
</style>
