<template>
  <v-app>
    <v-toolbar app>
      <v-toolbar-title class="headline">
        <span>Gabos's Shiny </span>
        <span class="font-weight-light">CALCULATOR</span>
      </v-toolbar-title>
    </v-toolbar>
    <v-container>
      <Calculator></Calculator>
    </v-container>
  </v-app>
</template>

<script>
import Calculator from './components/Calculator'

export default {
  name: 'App',
  components: {
    Calculator
  },
  data () {
    return {
      //
    }
  }
}
</script>
