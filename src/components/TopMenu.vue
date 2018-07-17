<template>
  <header class="menu-container">
    <div class="mobile-banner">
      
    </div>
    <div class="desktop-banner">
      <desk-top-menu
        :menu-list="menuList"
        :logo-img="logoImg"/>
    </div>
  </header>
</template>

<script>
import DeskTopMenu from './DeskTopMenu/DeskTopMenu'
export default {
  name: 'TopMenu',
  components: {
    DeskTopMenu
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
  mounted () {
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
</style>
