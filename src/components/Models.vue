<template>
    <div class="Models">
      <div class="Model3"/>
      <div class="ModelS"/>
      <div class="ModelX"/>
      <div class="ModelY"/>
      <div class="SolarPanels"/>
      <div class="Accessories"/>
        <!-- <h1 class="ModelY__title">Model Y</h1>
        <p class="ModelY__subtitle">Order Online for <a class="ModelY__subtitle__desc underline" href="#">Touchless Delivery</a></p> -->
        <!-- <img class="ModelY__background" src="../img/desktop_model_3_v2.jpg"/> -->
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

<style scoped>
.Models {
  max-height: 100vh;
  overflow-y: scroll;
  scroll-snap-type: y mandatory;
}
.Models div {
  scroll-snap-align: start;
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
