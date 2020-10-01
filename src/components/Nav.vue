<template>
  <div class="nav__bar">
    <img class="nav__bar__logo" src="../assets/tesla.svg"/>
    <ul class="nav__bar_center">
      <li v-for="element in elements" :key="element.name">
        <a href="#" v-on:click="add">
          {{ element.name }}
        </a>
      </li>
    </ul>
    <ul class="nav__bar_right">
      <li><a href="#">SHOP</a></li>
      <li><a href="#">CONNEXION</a></li>
    </ul>
    <Burger v-bind:more="more" v-bind:elements="elements"/>
  </div>
</template>

<script>
import Burger from '@/components/Burger'

export default {
  name: 'Nav',
  components: { Burger },
  data () {
    return {
      more: false,
      elements: [{
        name: 'MODEL S',
        type: 'link'
      },
      {
        name: 'MODEL X',
        type: 'link'
      },
      {
        name: 'MODEL 3',
        type: 'link'
      },
      {
        name: 'MODEL Y',
        type: 'link'
      },
      {
        name: 'POWERWALL',
        type: 'link'
      },
      {
        name: 'RECHARGER',
        type: 'link'
      },
      {
        name: 'PLUS',
        type: 'img',
        class: 'arrow'
      },
      {
        name: "VÉHICULES D'OCCASION",
        type: 'link'
      },
      {
        name: 'REPRISE',
        type: 'link'
      },
      {
        name: 'CYBERTRUCK',
        type: 'link'
      },
      {
        name: 'ROADSTER',
        type: 'link'
      },
      {
        name: 'ÉNERGIE',
        type: 'link'
      },
      {
        name: 'ENTREPRISES',
        type: 'link'
      },
      {
        name: 'ESSAIS',
        type: 'link'
      },
      {
        name: 'NOUS TROUVER',
        type: 'link'
      },
      {
        name: 'ÉVÉNEMENTS',
        type: 'link'
      },
      {
        name: 'ASSISTANCE',
        type: 'link'
      },
      {
        name: 'SHOP',
        type: 'link'
      },
      {
        name: 'CONNEXION',
        type: 'link'
      },
      {
        name: 'FRANCE',
        type: 'link'
      }
      ]
    }
  },
  methods: {
    add: function () {
    }
  }
}
</script>
