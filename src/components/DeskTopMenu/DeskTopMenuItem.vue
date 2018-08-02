<template>
  <li class="desk-top-menu-item">
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
  name: 'DeskTopMenuItem',
  inject: ['rootMenu'],
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
    }
  }
}
</script>

<style scoped>
.desk-top-menu-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  margin: 0;
  list-style: none;
}
.desk-top-menu-item > .link-div {
  padding-right: 2rem;
  text-align: center;
  color: #fff;
}
.desk-top-menu-item > .link-div:hover {
  color: #0d0e0e;
}
.itemActive {
  color: #0d0e0e !important;
}
</style>
