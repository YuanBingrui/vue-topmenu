<template>
  <header class="menu-container">
    <div class="menu-container-body">
      <top-menu-brand href="/">
        <img v-if="logoImg" :src="logoImg">
        brand
      </top-menu-brand>
      <top-menu-nav>
        <top-menu-item index="1" href="#">MENU ONE</top-menu-item>
        <top-menu-item index="2" href="#">MENU TWO</top-menu-item>
        <top-menu-item index="3" href="#">MENU TWO TWO</top-menu-item>
        <top-sub-menu>
          <template slot="title">SUBMENU ONE</template>
          <top-menu-item
            v-for="(menu, index) in menuList"
            :key="index+ 'top-menu-item'"
            :href="menu.href"
            :index="'4-' + index">
            {{ menu.name }}
          </top-menu-item>
        </top-sub-menu>
      </top-menu-nav>
      <top-menu-aside>
        <top-menu-item index="5" href="#"><span class="menu-btn">SIGN IN</span></top-menu-item>
        <top-menu-item index="6" href="#"><span class="menu-btn">SIGN UP UP</span></top-menu-item>
        <top-sub-menu>
          <template slot="title">HELP</template>
          <top-menu-item index="7-1">HELP ONE</top-menu-item>
          <top-menu-item index="7-2">HELP TWO</top-menu-item>
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
    logoImg: {
      type: String
    },
    menuList: {
      validator: (val) => val instanceof Array
    }
  },
  data () {
    return {
      activeIndex: '1'
    }
  },
  provide () {
    return {
      rootMenu: this
    }
  },
  mounted: function () {
    if (this.primaryColor) {
      document.querySelector('.menu-container').style.setProperty('--primary-color', this.primaryColor)
    }
  },
  methods: {}
}
</script>

<style scoped>
.menu-container {
  --primary-color: '';
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
  color: #6b6b6b;
  height: 100%;
}
.menu-btn {
  padding: 7px 14px;
  background-color: #edeff0;
  border-radius: 14px;
}
</style>
