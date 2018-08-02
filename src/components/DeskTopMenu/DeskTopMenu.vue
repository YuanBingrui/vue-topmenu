<template>
  <div class="desk-menu-container">
    <desk-top-menu-brand :to="$attrs.logoImg.to">
      <img
        v-if="$attrs.logoImg"
        :src="$attrs.logoImg.src"
        :alt="$attrs.logoImg.name">
      {{ $attrs.logoImg.wordDes }}
    </desk-top-menu-brand>
    <div class="desk-menu-nav-list">
      <desk-top-menu-nav>
        <template v-for="(menuItem, index) in $attrs.menuList">
          <desk-top-menu-item
            v-if="!menuItem.subMenuList"
            :key="index+ 'desk-menu-item'"
            :index="index + '_nav'"
            :to="menuItem.to">
            {{ menuItem.name }}
          </desk-top-menu-item>
          <desk-top-sub-menu
            v-else
            :key="index+ 'desk-menu-item'">
            <template slot="title">{{ menuItem.name }}</template>
            <desk-top-menu-item
              v-for="(subMenuItem, subIndex) in menuItem.subMenuList"
              :key="subIndex+ 'desk-sub-menu-item'"
              :to="subMenuItem.to"
              :index="index + '-' + subIndex + '_nav'">
              {{ subMenuItem.name }}
            </desk-top-menu-item>
          </desk-top-sub-menu>
        </template>
      </desk-top-menu-nav>
      <desk-top-menu-aside>
        <template v-for="(asideMenuItem, asideIndex) in $attrs.asideMenuList">
          <desk-top-menu-item
            v-if="!asideMenuItem.subMenuList"
            :key="asideIndex+ 'desk-aside-menu-item'"
            :index="asideIndex + '_aside'"
            :to="asideMenuItem.to">
            <span class="desk-menu-btn">{{ asideMenuItem.name }}</span>
          </desk-top-menu-item>
          <desk-top-sub-menu
            v-else
            :key="asideIndex+ 'desk-aside-menu-item'">
            <template slot="title">{{ asideMenuItem.name }}</template>
            <desk-top-menu-item
              v-for="(asideSubMenuItem, asideSubIndex) in asideMenuItem.subMenuList"
              :key="asideSubIndex+ 'desk-aside-sub-menu-item'"
              :to="asideSubMenuItem.to"
              :index="asideIndex + '-' + asideSubIndex + '_aside'">
              {{ asideSubMenuItem.name }}
            </desk-top-menu-item>
          </desk-top-sub-menu>
        </template>
      </desk-top-menu-aside>
    </div>
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
.desk-menu-container {
  display: flex;
  padding: 0 40px;
  color: #fff;
  height: 100%;
}
.desk-menu-btn {
  padding: 7px 14px;
  background-color: #edeff0;
  border-radius: 14px;
}
@media (min-width: 1200px) {
  .desk-menu-nav-list {
    display: flex;
    width: 100%;
  }
}
@media (min-width: 768.01px) and (max-width: 1199.98px) {
  .desk-menu-nav-list {
    width: 100%;
    display: flex;
    flex-direction: column-reverse;
  }
}
@media (max-width: 768px) {
  .desk-menu-container {
    display: none;
  }
}
</style>
