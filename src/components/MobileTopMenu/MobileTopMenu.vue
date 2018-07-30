<template>
  <div class="mobile-menu-container-body">
    <div class="mobile-menu-btn">
      <svg aria-hidden="true" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512" height="50" width="50"><path d="M432 176H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16zM432 272H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16zM432 368H80c-8.8 0-16-7.2-16-16s7.2-16 16-16h352c8.8 0 16 7.2 16 16s-7.2 16-16 16z"/></svg>
    </div>
    <mobile-top-menu-brand href="/">
      <img v-if="$attrs.logoImg" :src="$attrs.logoImg">
      brand
    </mobile-top-menu-brand>
    <div class="mobile-menu-block"></div>
  </div>
</template>

<script>
import MobileTopMenuBrand from './MobileTopMenuBrand'

export default {
  name: 'MobileTopMenu',
  components: {
    MobileTopMenuBrand,
  },
  data () {
    return {}
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped>
.mobile-menu-container-body {
  display: none;
}
@media (max-width: 768px) {
  .mobile-menu-container-body {
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
</style>
