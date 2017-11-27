<template>
  <div id="app">
    <topMenu :menu-data="menuData"/>
    <carousel :carousel-data="carouselData"/>
  </div>
</template>

<script>
import topMenu from './components/topMenu'
import carousel from './components/carousel'
export default {
  name: 'app',
  components: {
    topMenu,
    carousel
  },
  data () {
    return {
      menuData: {
        primaryColor: '',
        slideSpeed: '',
        logoImg: '../../static/logo.png',
        menuArr: [{name: 'Core Docs', href: '#'}, {name: 'Forum', href: '#'}, {name: 'Community', href: '#'}, {name: 'Twitter', href: '#'}, {name: 'Vue Router', href: '#'}, {name: 'Vuex', href: '#'}, {name: 'Typescript', href: '#'}]
      },
      carouselData: {}
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
