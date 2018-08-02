<template>
  <li class="mobile-top-menu-item">
    <div
      class="link-div"
      :class="{ itemActive: this.rootMenu.activeIndex === this.index }"
      @click="addActiveClass()">
      <slot></slot>
    </div>
  </li>
</template>

<script>
export default {
  name: 'MobileTopMenuItem',
  inject: ['rootMenu', 'mobileRootMenu'],
  props: {
    to: {
      default: ''
    },
    index: {
      type: String,
      default: ''
    }
  },
  methods: {
    addActiveClass () {
      this.rootMenu.activeIndex = this.index
      this.rootMenu.handleItemClick(this.to)
      this.mobileRootMenu.closeSideMenu()
    }
  }
}
</script>

<style scoped>
.mobile-top-menu-item {
  display: flex;
  justify-content: center;
  align-items: center;
  list-style: none;
  padding: 18px 0;
  color: #6b6b6b;
}
.mobile-top-menu-item > .link-div {
  width: 100%;
  text-align: left;
  color: #6b6b6b;
}
.mobile-top-menu-item > .link-div:hover {
  color: #0d0e0e;
}
.itemActive {
  color: #0d0e0e !important;
}
</style>
