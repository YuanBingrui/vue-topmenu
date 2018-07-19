<template>
  <div class="desk-menu-container-body">
    <desk-top-menu-brand href="/">
      <img v-if="$attrs.logoImg" :src="$attrs.logoImg">
      brand
    </desk-top-menu-brand>
    <desk-top-menu-nav>
      <desk-top-menu-item index="1" href="#">MENU ONE</desk-top-menu-item>
      <desk-top-menu-item index="2" href="#">MENU TWO</desk-top-menu-item>
      <desk-top-menu-item index="3" href="#">MENU TWO TWO</desk-top-menu-item>
      <desk-top-sub-menu>
        <template slot="title">SUBMENU ONE</template>
        <desk-top-menu-item
          v-for="(menu, index) in $attrs.menuList"
          :key="index+ 'desk-top-menu-item'"
          :href="menu.href"
          :index="'4-' + index">
          {{ menu.name }}
        </desk-top-menu-item>
      </desk-top-sub-menu>
    </desk-top-menu-nav>
    <desk-top-menu-aside>
      <desk-top-menu-item index="5" href="#">
        <span class="desk-menu-btn">SIGN IN</span>
      </desk-top-menu-item>
      <desk-top-menu-item index="6" href="#">
        <span class="desk-menu-btn">SIGN UP UP</span>
      </desk-top-menu-item>
      <desk-top-sub-menu>
        <template slot="title">HELP</template>
        <desk-top-menu-item index="7-1">HELP ONE</desk-top-menu-item>
        <desk-top-menu-item index="7-2">HELP TWO</desk-top-menu-item>
      </desk-top-sub-menu>
    </desk-top-menu-aside>
  </div>
</template>

<script>
import DeskTopMenuBrand from './DeskTopMenuBrand'
import DeskTopMenuNav from './DeskTopMenuNav'
import DeskTopMenuAside from './DeskTopMenuAside'
import DeskTopSubMenu from './DeskTopSubMenu'
import DeskTopMenuItem from './DeskTopMenuItem'

export default {
  name: 'DeskTopMenu',
  components: {
    DeskTopMenuBrand,
    DeskTopMenuItem,
    DeskTopSubMenu,
    DeskTopMenuNav,
    DeskTopMenuAside
  },
  inheritAttrs: false,
  data () {
    return {}
  },
  created () {
    console.log(this.$attrs)
  },
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
@media (max-width: 576px) {
  .desk-menu-container-body {
    display: none;
  }
}
</style>
