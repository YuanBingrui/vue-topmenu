<template>
  <div id="app">
    <top-menu
      :menu-list="menuData.menuList"
      :logo-img="menuData.logoImg"/>
    <div class="content-container">sddsfsd</div>
  </div>
</template>

<script>
import TopMenu from './components/TopMenu'

export default {
  name: 'app',
  components: {
    TopMenu
  },
  data () {
    return {
      menuData: {
        primaryColor: '',
        logoImg: '../../static/logo.png',
        menuList: [
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
.content-container {
  margin-top: 105px;
}
</style>
