<template>
  <div class="nav__bar">
    <img class="nav__bar__logo" src="../assets/tesla.svg"/>
    <ul class="nav__bar_center" v-html="nav"></ul>
    <ul class="nav__bar_right">
      <li><a href="#">SHOP</a></li>
      <li><a href="#">CONNEXION</a></li>
    </ul>
    <Burger v-bind:nav="nav"/>
  </div>
</template>

<script>
import Burger from '@/components/Burger'

export default {
  name: 'Nav',
  components: { Burger },
  data () {
    return {
      nav: `
        <li class="test"><a href="#S">MODEL S</a></li>
        <li><a href="#">MODEL X</a></li>
        <li><a href="#">MODEL 3</a></li>
        <li><a href="#">MODEL Y</a></li>
        <li><a href="#">POWERWALL</a></li>
        <li><a href="#">RECHARGER</a></li>
        <li><a href="#">PLUS</a></li>
        <li><a href="#">VÉHICULES D'OCCASION</a></li>
        <li><a href="#">REPRISE</a></li>
        <li><a href="#">CYBERTRUCK</a></li>
        <li><a href="#">ROADSTER</a></li>
        <li><a href="#">ÉNERGIE</a></li>
        <li><a href="#">ENTREPRISES</a></li>
        <li><a href="#">ESSAIS</a></li>
        <li><a href="#">NOUS TROUVER</a></li>
        <li><a href="#">ÉVÉNEMENTS</a></li>
        <li><a href="#">ASSISTANCE</a></li>
        <li><a href="#">FRANCE</a></li>
        <li><a href="#">SHOP</a></li>
        <li><a href="#">CONNEXION</a></li>`
    }
  },
  methods: {
    add: function () {
      this.count++
    }
  }
}
</script>
