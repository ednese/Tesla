<template>
  <div class="burger" v-on:click="toggle" v-bind:class="{active: isActive, disable: isActive}">
      <span/>
  </div>
</template>

<script>
export default {
  name: 'Burger',
  data () {
    return {
      isActive: true
    }
  },
  methods: {
    toggle: () => {
      this.isActive = !this.isActive
      console.log(this.isActive)
    }
  }
}
</script>

<style scoped>
.burger {
    height: 24px;
    width: 25px;
    margin: 14px;
    cursor: pointer;
    position: relative;
}
.burger span {
    height: 2px;
    width: 100%;
    display: block;
    position: absolute;
    top: 50%; transform: translateY(-50%);
    background-color: rgb(0, 0, 0);
}
.burger span::before, .burger span::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: rgb(0, 0, 0);
}
.burger span::before {
    transform: translateY(-6px);
}
.burger span::after {
    transform: translateY(6px);
}
</style>
