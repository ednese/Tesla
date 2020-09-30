<template>
  <div class="nav__bar">
    <img class="nav__bar__logo" src="../assets/tesla.svg"/>
    <ul class="nav__bar_center">
      <li><a href="#S">MODEL S</a></li>
      <li><a href="#">MODEL 3</a></li>
      <li><a href="#">MODEL X</a></li>
      <li><a href="#">MODEL Y</a></li>
      <li><a href="#">POWERWALL</a></li>
      <li><a href="#">RECHARGER</a></li>
    </ul>
    <ul class="nav__bar_right">
      <li><a href="#">SHOP</a></li>
      <li><a href="#">CONNEXION</a></li>
    </ul>
    <Burger/>
  </div>
</template>

<script>
import Burger from '@/components/Burger'

export default {
  name: 'Nav',
  components: { Burger },
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
