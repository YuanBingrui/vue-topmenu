<template>
  <div id="app">
    <top-menu :menu-arr="menuData.menuArr" :logo-img="menuData.logoImg"/>
  </div>
</template>

<script>
import TopMenu from './components/TopMenu/TopMenu'

export default {
  name: 'app',
  components: {
    TopMenu
  },
  data () {
    return {
      menuData: {
        primaryColor: '',
        slideSpeed: '',
        logoImg: '../../static/logo.png',
        menuArr: [
          { name: 'Core Docs', href: '#' },
          { name: 'Forum', href: '#' },
          { name: 'Community', href: '#' },
          { name: 'Twitter', href: '#' }
        ]
      }
    }
  },
  created () {},
  methods: {}
}
</script>

<style>
body {
  margin: 0 !important;
}
#app {
  height: 1000px;
  border: 1px #fff solid;
}
</style>
