<template>
    <div class="Models">
      <div v-if="fadein" class="fadein"/>
      <div v-for="item in items" :key="item.name" v-bind:class="item.type">
        <h1 on class="Models__title" v-bind:style="{opacity: opacity}">{{item.title}}</h1>
        <a v-if="item.class === 'inputs'" @mouseover="hover" @mouseout="hover" v-bind:class="{bold:bold}" class="Models__subtitle">Contacter un Store</a>
        <h2 v-else-if="item.type === 'SolarPanels'" class="Models__subtitle">{{item.subtitle}}</h2>
        <div v-if="item.class === 'inputs'" class="inputs">
          <button class="Models__input_black">CONFIGURATION PERSONNALISÉE</button>
          <button class="Models__input_white">VÉHICULES DISPONIBLES</button>
        </div>
        <button v-else-if="item.class === 'infos'" class="Models__input_infos">EN SAVOIR PLUS</button>
        <button v-else class="Models__input_buy">COMMANDER MAINTENANT</button>
        <div v-if="item.class === 'buy'"><Footer/></div>
      </div>
    </div>
</template>

<script>
import Footer from '@/components/Footer'

import '@/style/models.css'
import '@/style/models-responsive.css'

export default {
  name: 'Models',
  components: { Footer },
  data () {
    const title = [{title: 'Model 3', type: 'Model3'}, {title: 'Model S', type: 'ModelS'}, {title: 'Model X', type: 'ModelX'}, {title: 'Model Y', type: 'ModelY'}, {title: "Systèmes d'énergie solaire et Powerwalls", type: 'SolarPanels'}, {title: 'Accessoires', type: 'Accessories'}]
    const parse = tab => tab.map((item, index) => {
      const obj = {}
      obj.title = item.title
      obj.class = 'infos'
      obj.type = item.type
      if (index < 3) {
        obj.subtitle = 'Contacter un Store'
        obj.class = 'inputs'
      } else if (index === 4) {
        obj.subtitle = 'De l’énergie pour tous vos besoins'
      } else if (index === 5) {
        obj.class = 'buy'
      }
      return obj
    })
    return {
      bold: false,
      fadein: false,
      items: parse(title),
      opacity: 1
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
