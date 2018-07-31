<template>
  <header class="menu-container menu-container-sm menu-container-md menu-container-lg">
    <desk-top-menu v-bind="$attrs"/>
    <mobile-top-menu v-bind="$attrs"/>
  </header>
</template>

<script>
import DeskTopMenu from './DeskTopMenu/DeskTopMenu'
import MobileTopMenu from './MobileTopMenu/MobileTopMenu'
export default {
  name: 'TopMenu',
  components: {
    DeskTopMenu,
    MobileTopMenu
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
    this.bindScollEvent()
  },
  methods: {
    bindScollEvent () {}
  }
}
</script>

<style scoped>
.menu-container {
  --primary-color: '';
  width: 100%;
  background: #f8f4e6;
  position: fixed;
  z-index: 3;
  top: 0;
  left: 0;
}
@media (min-width: 1200px) {
  .menu-container-lg {
    height: 100px;
  }
}
@media (min-width: 768.01px) and (max-width: 1199.98px) {
  .menu-container-md {
    height: 100px;
  }
}
@media (max-width: 768px) {
  .menu-container-sm {
    height: 70px;
  }
}
</style>
