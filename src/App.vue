<template>
  <div id="app">
    <topMenu :menu-data="menuData"/>
  </div>
</template>

<script>
import topMenu from './components/topMenu'
export default {
  name: 'app',
  components: {
    topMenu
  },
  data () {
    return {
      menuData: {
        primaryColor: '',
        menuArr: [{name: 'menu01', value: 'Core Docs'}, {name: 'menu02', value: 'Forum'}, {name: 'menu03', value: 'Community'}, {name: 'menu04', value: 'Twitter'}, {name: 'menu05', value: 'Vue Router'}, {name: 'menu06', value: 'Vuex'}, {name: 'menu06', value: 'Typescript'}]
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
</style>
