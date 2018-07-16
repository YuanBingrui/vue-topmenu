<template>
  <aside class="top-menu-aside">
    <ul class="top-menu-aside-body">
      <slot></slot>
    </ul>
  </aside>
</template>

<script>
export default {
  name: 'TopMenuAside',
  data () {
    return {}
  },
  created () {},
  methods: {}
}
</script>

<style scoped>
.top-menu-aside {
  width: 25%;
  box-sizing: border-box;
}
.top-menu-aside-body {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
  height: 100%;
}
</style>
