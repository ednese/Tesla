<template>
  <div class="burger">
    <div class="burger__icon" v-on:click="toggle" v-bind:class="{active: isActive}">
      <span/>
    </div>
    <ul class="burger__sidebar" v-bind:class="{open: isActive, close: isDisable, more: more}">
      <li v-bind:class="{more: more}" v-for="element in elements" :key="element.name">
        <a v-if="element.type !== 'img'" v-bind:href="element.name">
          {{ element.name }}
        </a>
        <a v-else-if="element.type === 'img'" href="#" v-on:click="moreEvent">
          {{ element.name }}
          <img v-bind:class="element.class" src="@/assets/arrow.png"/>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
import '@/style/burger.css'
import '@/style/burger_responsive.css'

export default {
  name: 'Burger',
  props: ['elements'],
  data () {
    document.addEventListener('scroll', () => {
      if (this.isActive === true && window.scrollY > 1) {
        this.isActive = false
        this.isDisable = true
        this.more = false
      }
    })
    return {
      isActive: undefined,
      isDisable: false,
      more: false
    }
  },
  methods: {
    toggle: function () {
      if (this.isActive === undefined) {
        this.isActive = true
      } else {
        this.isActive = !this.isActive
        this.isDisable = !this.isDisable
      }
      if (this.isActive === false) {
        this.more = false
      }
    },
    moreEvent: function () {
      this.more = !this.more
    }
  }
}
</script>
