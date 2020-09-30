<template>
  <div class="burger">
    <div class="burger__icon" v-on:click="toggle" v-bind:class="{active: isActive}">
      <span/>
    </div>
    <ul class="burger__sidebar" v-bind:class="{open: isActive, close: isDisable}">
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
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Burger',
  data () {
    return {
      isActive: undefined,
      isDisable: false
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
    }
  }
}
</script>

<style scoped>
.burger__icon {
    height: 24px;
    width: 25px;
    margin: 14px;
    cursor: pointer;
    z-index: 1;
    position: relative;
}
.burger__icon span {
    height: 2px;
    width: 100%;
    display: block;
    position: absolute;
    top: 50%; transform: translateY(-50%);
    background-color: rgb(0, 0, 0);
    transition: all ease-in-out .1s;
}
.burger__icon span::before, .burger__icon span::after {
    content: '';
    position: absolute;
    width: 100%;
    height: 2px;
    background-color: rgb(0, 0, 0);
}
.burger__icon span::before {
    transform: translateY(-6px);
    transition: all ease-in-out .3s;
}
.burger__icon span::after {
    transform: translateY(6px);
    transition: all ease-in-out .3s;
}
.burger__icon.active span{
    background-color: rgba(0, 0, 0, 0);
}

.burger__icon.active span::before {
    transform: translateY(0px) rotateZ(45deg);
}
.burger__icon.active span::after {
    transform: translateY(0px) rotateZ(-45deg);
}
.burger__sidebar {
  position: absolute;
  background: rgb(196, 190, 190);
  height: 100vh;
  top: 0;right: 0;margin: 0 -400px 0 0;;
}
.burger__sidebar.open {
  top: 0;right: 0;margin: 0 -400px 0 0;
  animation: side-open 1s forwards;
}
@keyframes side-open {
    100% {margin: 0 0px 0 0;}
}
.burger__sidebar.close {
  top: 0;right: 0;margin: 0 0px 0 0;
  animation: side-close 1s forwards;
}
@keyframes side-close {
    100% {margin: 0 -400px 0 0;}
}
.burger__sidebar li:first-child{
  margin-top: 80px;
}
.burger__sidebar li{
  display: flex;
  flex-direction: row;
  margin: 40px 100px 0px 40px;
}
.burger__sidebar li::after{
  content: '';
  position: absolute;
  width: 80%;
  left: 35px;
  margin-top: 40px;
  height: 1px;
  background-color: rgb(0, 0, 0);
}
</style>
