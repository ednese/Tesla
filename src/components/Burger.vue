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
export default {
  name: 'Burger',
  props: ['elements'],
  data () {
    document.addEventListener('scroll', () => {
      if (this.isActive === true) {
        this.isActive = false
        this.isDisable = true
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
  width: 350px;
  display: flex;
  flex-direction: column;
  top: 0;right: 0;margin: 0 -400px 0 0;;
}
.burger__sidebar.open {
  top: 0;right: 0;margin: 0 -400px 0 0;
  animation: side-open .5s forwards;
}
@keyframes side-open {
    100% {margin: 0 0px 0 0;}
}
.burger__sidebar.close {
  top: 0;right: 0;margin: 0 0px 0 0;
  animation: side-close .5s forwards;
}
@keyframes side-close {
    100% {margin: 0 -400px 0 0;}
}
.burger__sidebar >>> li:nth-child(8){
  margin-top: 80px;
}
.burger__sidebar >>> li{
  margin: 40px 100px 0px 40px;
}
.burger__sidebar >>> li::after{
  content: '';
  position: absolute;
  width: 80%;
  left: 35px;
  margin-top: 40px;
  height: 1px;
  background-color: rgb(0, 0, 0);
}

.burger__sidebar >>> li:nth-child(-n+7),
.burger__sidebar >>> li:nth-child(n+21),
.burger__sidebar >>> li:nth-child(18),
.burger__sidebar >>> li:nth-child(19) {
  display: none;
}
@media screen and (max-width: 1200px) {
    .burger__sidebar >>> li:nth-child(1n) {
      display: block;
    }
    .burger__sidebar >>> li:nth-child(n+8) {
      display: none;
    }
    .burger__sidebar >>> li:nth-child(7),
    .burger__sidebar >>> li:nth-child(20) {
      display: block;
      order: 3;
    }
    .burger__sidebar >>> li:nth-child(18) {
      display: block;
      order: 2;
    }
    .burger__sidebar >>> li:nth-child(1) {
      margin-top: 80px;
    }
    .burger__sidebar >>> li>a>img.arrow {
      width: 8px;
      transform: rotate(0deg);
    }
    .burger__sidebar.more >>> li>a>img.arrow {
      transform: rotate(90deg);
      width: 10px;
    }
    .burger__sidebar.more >>> li:nth-child(-n+6) {
      display: none;
    }
    .burger__sidebar.more >>> li:nth-child(n+7) {
      display: block;
      order: 1;
    }
    .burger__sidebar.more >>> li:nth-child(18) {
      display: none;
    }
    .burger__sidebar.more >>> li:nth-child(8) {
      margin-top: 40px;
    }
    .burger__sidebar.more >>> li:nth-child(7) {
      margin-top: 80px;
      font-weight: 700;
    }
}
</style>
