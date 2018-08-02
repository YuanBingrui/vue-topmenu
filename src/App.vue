<template>
  <div id="app">
    <top-menu
      :primary-color="menuData.primaryColor"
      :menuList="menuData.menuList"
      :logoImg="menuData.logoImg"
      :asideMenuList="menuData.asideMenuList"/>
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
        primaryColor: '#38b48b',
        logoImg: {
          name: 'logo',
          src: require('./assets/logo.png'),
          to: '/',
          wordDes: 'brand'
        },
        menuList: [
          { name: 'HOME', to: '/' },
          {
            name: 'PRIVATE DATA',
            subMenuList: [
              { name: 'ADD DATA', to: '/private_data' },
              { name: 'VIEW DATA', to: '' }
            ]
          },
          { name: 'ABOUT', to: '/about' }
        ],
        asideMenuList: [
          { name: 'LOGIN', to: '/login' },
          { name: 'LOGOUT', to: '' },
          {
            name: 'HELP',
            subMenuList: [
              { name: 'HELP INFO', to: '/help' },
              { name: 'HELP FUNCTION', to: '' }
            ]
          }
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
/*.content-container {
  margin-top: 105px;
}*/
</style>
