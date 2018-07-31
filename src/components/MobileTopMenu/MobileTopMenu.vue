<template>
  <div class="mobile-menu-container">
    <div
      class="mobile-menu-btn"
      @click="toggleMenu">
      <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" height="50" width="50"><path d="M432 176H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16zM432 272H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16zM432 368H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16z"/></svg>
    </div>
    <mobile-top-menu-brand href="/">
      <img v-if="$attrs.logoImg" :src="$attrs.logoImg">
      brand
    </mobile-top-menu-brand>
    <div class="mobile-menu-block"></div>
    <div class="mobile-menu-container-body" ref="mobileMenuBody">
      <div class="mobile-menu-container-body-header">
        <div
          class="mobile-menu-btn"
          @click="toggleMenu">
          <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" height="50" width="50"><path d="M278.6 256l68.2-68.2c6.2-6.2 6.2-16.4 0-22.6-6.2-6.2-16.4-6.2-22.6 0L256 233.4l-68.2-68.2c-6.2-6.2-16.4-6.2-22.6 0-3.1 3.1-4.7 7.2-4.7 11.3 0 4.1 1.6 8.2 4.7 11.3l68.2 68.2-68.2 68.2c-3.1 3.1-4.7 7.2-4.7 11.3 0 4.1 1.6 8.2 4.7 11.3 6.2 6.2 16.4 6.2 22.6 0l68.2-68.2 68.2 68.2c6.2 6.2 16.4 6.2 22.6 0 6.2-6.2 6.2-16.4 0-22.6L278.6 256z"/></svg>
        </div>
        <mobile-top-menu-brand href="/">
          <img v-if="$attrs.logoImg" :src="$attrs.logoImg">
          brand
        </mobile-top-menu-brand>
        <div class="mobile-menu-block"></div>
      </div>
      <div class="mobile-menu-container-body-content">
        <div class="mobile-menu-container-body-content-bottom">
          <mobile-top-menu-item index="6" href="#">
            <span class="mobile-menu-content-btn">SIGN IN</span>
          </mobile-top-menu-item>
          <mobile-top-menu-item index="7" href="#">
            <span class="mobile-menu-content-btn">SIGN UP UP</span>
          </mobile-top-menu-item>
        </div>
        <mobile-top-menu-nav>
          <mobile-top-menu-item index="1" href="#" class="mobile-menu-border">MENU ONE</mobile-top-menu-item>
          <mobile-top-menu-item index="2" href="#" class="mobile-menu-border">MENU TWO</mobile-top-menu-item>
          <mobile-top-menu-item index="3" href="#" class="mobile-menu-border">MENU TWO TWO</mobile-top-menu-item>
          <mobile-top-sub-menu :menu-num="$attrs.menuList.length">
            <template slot="mobile-title">SUBMENU ONE</template>
            <mobile-top-menu-item
              v-for="(menu, index) in $attrs.menuList"
              :key="index+ 'mobile-top-menu-item'"
              :href="menu.href"
              :index="'4-' + index">
              {{ menu.name }}
            </mobile-top-menu-item>
          </mobile-top-sub-menu>
          <mobile-top-menu-item index="5" href="#" class="mobile-menu-border">MENU TWO TWO</mobile-top-menu-item>
          <mobile-top-sub-menu :menu-num="$attrs.menuList.length">
            <template slot="mobile-title">SUBMENU ONE</template>
            <mobile-top-menu-item
              v-for="(menu, index) in $attrs.menuList"
              :key="index+ 'mobile-top-menu-item'"
              :href="menu.href"
              :index="'4-' + index">
              {{ menu.name }}
            </mobile-top-menu-item>
          </mobile-top-sub-menu>
        </mobile-top-menu-nav>
      </div>
    </div>
  </div>
</template>

<script>
import MobileTopMenuBrand from './MobileTopMenuBrand'
import MobileTopMenuNav from './MobileTopMenuNav'
import MobileTopSubMenu from './MobileTopSubMenu'
import MobileTopMenuItem from './MobileTopMenuItem'

export default {
  name: 'MobileTopMenu',
  components: {
    MobileTopMenuBrand,
    MobileTopMenuNav,
    MobileTopSubMenu,
    MobileTopMenuItem
  },
  data () {
    return {
      isClose: true
    }
  },
  methods: {
    toggleMenu (targetEl, el) {
      if (this.isClose) {
        this.addStyle(this.$refs.mobileMenuBody)
        this.isClose = false
      } else {
        this.removeStyle(this.$refs.mobileMenuBody)
        this.isClose = true
      }
    },
    addStyle (el) {
      el.style.transform = 'scale(1, 1)'
      el.style.transformOrigin = '0 0'
    },
    removeStyle (el) {
      el.style.transform = 'scale(0, 1)'
    }
  }
}
</script>

<style scoped>
.mobile-menu-container {
  display: none;
}
@media (max-width: 768px) {
  .mobile-menu-container {
    display: flex;
    height: 100%;
  }
}
.mobile-menu-btn, .mobile-menu-block {
  width: 20%;
  display: flex;
  align-items: center;
  justify-content: center;
}
.mobile-menu-container-body {
  width: 100vw;
  position: absolute;
  top: 0;
  left: 0;
  transform: scale(0, 1);
  transition: transform .3s;
  
}
.mobile-menu-container-body-header {
  height: 70px;
  display: flex;
  background: #bf242a;
}
.mobile-menu-container-body-content {
  background: #f8f4e6;
  width: 100%;
  height: calc(100vh - 70px);
  padding-bottom: 10px;
  overflow: auto;
}
.mobile-menu-border {
  border-top: 1px solid #000;
}
.mobile-menu-border:first-child {
  border-top: none;
}
.mobile-menu-container-body-content-bottom {
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding-top: 7px;
}
.mobile-menu-content-btn {
  width: 100%;
  padding: 7px 14px;
  background-color: #edeff0;
  border-radius: 14px;
  text-align: center;
}
</style>
