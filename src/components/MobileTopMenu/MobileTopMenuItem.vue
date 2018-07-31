<template>
  <li class="mobile-top-menu-item">
    <a
      :href="href"
      :class="{ itemActive: this.rootMenu.activeIndex === this.index }"
      @click="addActiveClass()">
      <slot></slot>
    </a>
  </li>
</template>

<script>
export default {
  name: 'MobileTopMenuItem',
  inject: ['rootMenu'],
  props: {
    href: {
      type: String,
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
.mobile-top-menu-item > a {
  width: 100%;
  text-decoration: none;
  text-align: left;
  color: #6b6b6b;
}
.mobile-top-menu-item > a:hover {
  color: #0d0e0e;
}
.itemActive {
  color: #0d0e0e !important;
}
</style>
