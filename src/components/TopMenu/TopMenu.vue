<template>
  <header class="menu-container">
    <div class="menu-container-body">
      <top-menu-brand href="/">
        <img v-if="logoImg" :src="logoImg">
          brand
      </top-menu-brand>
      <top-menu-nav>
        <top-menu-item href="/">MENU ONE</top-menu-item>
        <top-menu-item href="/">MENU TWO</top-menu-item>
        <top-menu-item href="/">MENU TWO</top-menu-item>
        <top-sub-menu>
          <template slot="title">SUBMENU ONE</template>
          <top-menu-item
            v-for="(menu, index) in menuArr"
            :key="index+ 'top-menu-item'"
            :href="menu.href">
            {{ menu.name }}
          </top-menu-item>
        </top-sub-menu>
      </top-menu-nav>
      <top-menu-aside>
        <top-menu-item href="/">SIGN IN</top-menu-item>
        <top-menu-item href="/">SIGN UP</top-menu-item>
        <top-sub-menu>
          <template slot="title">HELP</template>
          <top-menu-item>HELP ONE</top-menu-item>
          <top-menu-item>HELP TWO</top-menu-item>
        </top-sub-menu>
      </top-menu-aside>
    </div>
  </header>
</template>

<script>
import TopMenuBrand from './TopMenuBrand'
import TopMenuNav from './TopMenuNav'
import TopMenuAside from './TopMenuAside'
import TopSubMenu from './TopSubMenu'
import TopMenuItem from './TopMenuItem'

export default {
  name: 'TopMenu',
  components: {
    TopMenuBrand,
    TopMenuItem,
    TopSubMenu,
    TopMenuNav,
    TopMenuAside
  },
  props: {
    primaryColor: {
      type: String,
      default: '#42b983'
    },
    slideSpeed: {
      type: String,
      default: '0.7s'
    },
    logoImg: {
      type: String
    },
    menuArr: {
      validator: (val) => val instanceof Array
    }
  },
  data () {
    return {
      menuIndex: 0,
      leftValue: 0
    }
  },
  mounted: function () {
    if (this.primaryColor) {
      document.querySelector('.menu-container').style.setProperty('--primary-color', this.primaryColor)
    }
    if (this.slideSpeed) {
      document.querySelector('.menu-container').style.setProperty('--slide-speed', this.slideSpeed)
    }
  },
  methods: {}
}
</script>

<style scoped>
.menu-container {
  --primary-color: '';
  --slide-speed: '';
  width: 100%;
  background: #f7f9fa;
  position: fixed;
  z-index: 3;
  top: 0;
  left: 0;
  height: 105px;
  border-bottom: 1px solid #d4d6d6;
}
.menu-container-body {
  display: flex;
  padding: 0 40px;
  /*box-sizing: border-box;*/
  color: #6b6b6b;
  height: 100%;
}
</style>
