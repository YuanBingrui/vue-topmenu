<template>
  <div class="desk-menu-container-body">
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
      <top-menu-item index="5" href="#"><span class="desk-menu-btn">SIGN IN</span></top-menu-item>
      <top-menu-item index="6" href="#"><span class="desk-menu-btn">SIGN UP UP</span></top-menu-item>
      <top-sub-menu>
        <template slot="title">HELP</template>
        <top-menu-item index="7-1">HELP ONE</top-menu-item>
        <top-menu-item index="7-2">HELP TWO</top-menu-item>
      </top-sub-menu>
    </top-menu-aside>
  </div>
</template>

<script>
import DeskTopMenuBrand from './TopMenuBrand'
import DeskTopMenuNav from './TopMenuNav'
import DeskTopMenuAside from './TopMenuAside'
import DeskTopSubMenu from './TopSubMenu'
import DeskTopMenuItem from './TopMenuItem'

export default {
  name: 'DeskTopMenu',
  components: {
    TopMenuBrand,
    TopMenuItem,
    TopSubMenu,
    TopMenuNav,
    TopMenuAside
  },
  data () {
    return {

    }
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped>
.desk-menu-container-body {
  display: flex;
  padding: 0 40px;
  color: #6b6b6b;
  height: 100%;
}
.desk-menu-btn {
  padding: 7px 14px;
  background-color: #edeff0;
  border-radius: 14px;
}
</style>
