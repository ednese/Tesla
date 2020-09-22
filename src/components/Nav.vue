<template>
  <div id="nav">
    <div class="nav__bar">
      <img class="nav__bar__logo" src="../assets/tesla.svg"/>
      <ul class="nav__bar_center">
        <li><a href="#">MODEL S</a></li>
        <li><a href="#">MODEL 3</a></li>
        <li><a href="#">MODEL X</a></li>
        <li><a href="#">MODEL Y</a></li>
        <li><a href="#">SOLAR ROOF</a></li>
        <li><a href="#">SOLAR PANELS</a></li>
      </ul>
      <ul class="nav__bar_right">
        <li><a href="#">SHOP</a></li>
        <li><a href="#">SIGN IN</a></li>
      </ul>
    </div>
    <h1 class="nav__title">Model Y</h1>
    <p class="nav__title__desc">Order Online for <a class="nav__title__desc_underline" href="#">Touchless Delivery</a></p>
    <img class="nav__background" src="../img/Desktop-ModelY.jpg"/>
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
