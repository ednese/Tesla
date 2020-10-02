<template>
    <div class="Models">
      <div class="Model3">
        <h1 on class="Model3__title">Model 3</h1>
        <a @mouseover="hover" @mouseout="hover" v-bind:class="{bold:bold}" class="Model3__subtitle">Contacter un Store</a>
        <div class="inputs">
          <button class="Model3__input_black">CONFIGURATION PERSONNALISÉE</button>
          <button class="Model3__input_white">VÉHICULES DISPONIBLES</button>
        </div>
      </div>
      <div class="ModelS">
        <h1 on class="Model3__title">Model 3</h1>
        <a @mouseover="hover" @mouseout="hover" v-bind:class="{bold:bold}" class="Model3__subtitle">Contacter un Store</a>
        <div class="inputs">
          <button class="Model3__input_black">CONFIGURATION PERSONNALISÉE</button>
          <button class="Model3__input_white">VÉHICULES DISPONIBLES</button>
        </div>
      </div>
      <div class="ModelX"/>
      <div class="ModelY"/>
      <div class="SolarPanels"/>
      <div class="Accessories"/>
    </div>
</template>

<script>
import '@/style/nav.css'
export default {
  name: 'Nav',
  data () {
    return {
      bold: false
    }
  },
  methods: {
    hover: function () {
      this.bold = !this.bold
      console.log('true')
    }
  }
}
</script>

<style scoped>
.Models {
  max-height: 100vh;
  overflow-y: scroll;
  scroll-snap-points-y: repeat(100vh);
  scroll-snap-type: y mandatory;
}
.Models > div {
  scroll-snap-align: start;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.Model3__title,
.Model3__subtitle {
  position: relative;
  bottom:270px;
  margin: 0;
}
.Model3__title {
  font-size: 40px;
  font-weight: 600;
}
.Model3__subtitle {
  font-size: 14px;
}
.Models>div>a{
  cursor: pointer;
}
.Models>div>a::after,
.Models>div>a.bold::after{
  content: '';
  display: flex;
  position: absolute;
  width: 100%;
  background-color: rgb(0, 0, 0);
  animation: mouse-over .5s forwards;
}
.Models>div>a::after{
  height: 1px;
}
.Models>div>a.bold::after{
  height: 2px;
}
.Model3__input_black,
.Model3__input_white {
  position: relative;
  top: 290px;
  cursor: pointer;
  border: none;
  font-family: Montserrat;
  font-weight: 500;
  border-radius: 50px;
  margin: 0 10px;
  height: 40px;
  width: 320px;
}
.Model3__input_black {
  color: white;
  background: rgba(0, 0, 0, 0.7);
}
.Model3__input_white {
  width: 250px;
  color: black;
  background: rgba(255, 255, 255, 0.7);
}
.Model3, .ModelS, .ModelX, .ModelY, .SolarPanels, .Accessories {
    width: 100%;
    height: 100vh;
    background-size: cover;
    background-position: center;
}
.Model3 {
    background-image: url("../img/desktop_model_3_v2.jpg");
}
.ModelS {
    background-image: url("../img/Desktop-ModelS.jpg");
}
.ModelX {
    background-image: url("../img/Desktop-ModelX.jpg");
}
.ModelY {
    background-image: url("../img/Desktop-ModelY.jpg");
}
.SolarPanels {
    background-image: url("../img/Desktop-SolarPanels.jpg");
}
.Accessories {
    background-image: url("../img/Desktop-Accessories.jpg");
}
</style>
