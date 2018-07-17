<template>
  <li class="top-menu-item">
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
  name: 'TopMenuItem',
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
.top-menu-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  margin: 0;
  list-style: none;
}
.top-menu-item > a {
  text-decoration: none;
  padding-right: 2rem;
  text-align: center;
  color: #6b6b6b;
}
.top-menu-item > a:hover {
  color: #0d0e0e;
}
.itemActive {
  color: #0d0e0e !important;
}
</style>
