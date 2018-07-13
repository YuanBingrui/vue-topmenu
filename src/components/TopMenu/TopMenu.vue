<template>
  <div class="menu-container">
    <ul class="menu-container-body">
      <top-menu-brand href="/">
        <img v-if="logoImg" :src="logoImg">
          brand
      </top-menu-brand>
      <top-menu-item href="/">
        <template slot="title">MENU ONE</template>
      </top-menu-item>
      <top-menu-item href="/">
        <template slot="title">MENU TWO</template>
      </top-menu-item>
      <top-menu-item href="/">
        <template slot="title">MENU TWO</template>
      </top-menu-item>
      <top-menu-item href="/">
        <template slot="title">MENU TWO</template>
      </top-menu-item>
      <top-sub-menu>
        <template slot="title">SUBMENU ONE</template>
        <top-menu-item
          v-for="(menu, index) in menuArr"
          :key="index+ 'top-menu-item'"
          :href="menu.href">
          <template slot="title">{{ menu.name }}</template>
        </top-menu-item>
      </top-sub-menu>
    <!-- <top-sub-menu class="top-right">
      <top-menu-item href="/">
        <template slot="title">sign in</template>
      </top-menu-item>
      <top-menu-item href="/">
        <template slot="title">sign up</template>
      </top-menu-item>
      <top-menu-item href="/">
        <template slot="title">help</template>
      </top-menu-item>
    </top-sub-menu> -->
  </ul>
  </div>
</template>

<script>
import TopMenuBrand from './TopMenuBrand'
import TopMenuItem from './TopMenuItem'
import TopSubMenu from './TopSubMenu'

export default {
  name: 'TopMenu',
  components: {
    TopMenuBrand,
    TopMenuItem,
    TopSubMenu
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
}
.menu-container-body {
  display: flex;
  /*justify-content: space-between;*/
  align-items: center;
  padding: 0.5rem 1rem;
}
</style>
