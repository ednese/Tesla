<template>
  <div class="nav__bar">
    <img class="nav__bar__logo" src="../assets/tesla.svg"/>
    <ul class="nav__bar_center">
      <li v-for="element in elements" :key="element.name">
        <a v-bind:href="element.name">
          {{ element.name }}
        </a>
      </li>
    </ul>
    <ul class="nav__bar_right">
      <li><a href="#">SHOP</a></li>
      <li><a href="#">CONNEXION</a></li>
    </ul>
    <Burger v-bind:elements="elements"/>
  </div>
</template>

<script>
import Burger from '@/components/Burger'

import '@/style/nav.css'

export default {
  name: 'Nav',
  components: { Burger },
  data () {
    const tab = ['MODEL S', 'MODEL X', 'MODEL 3', 'MODEL Y', 'POWERWALL', 'RECHARGER', 'PLUS', "VÉHICULES D'OCCASION", 'REPRISE', 'CYBERTRUCK', 'ROADSTER', 'ÉNERGIE', 'ENTREPRISES', 'ESSAIS', 'NOUS TROUVER', 'ÉVÉNEMENTS', 'ASSISTANCE', 'SHOP', 'CONNEXION', 'FRANCE']
    const parse = tab => tab.map(item => {
      const obj = {}
      obj.name = item
      if (item !== 'PLUS') {
        obj.type = 'link'
      } else {
        obj.type = 'img'
        obj.class = 'arrow'
      }
      return obj
    })
    return {
      elements: parse(tab)
    }
  }
}
</script>
