<template>
  <aside class="desk-top-menu-aside">
    <ul class="desk-top-menu-aside-body">
      <slot></slot>
    </ul>
  </aside>
</template>

<script>
export default {
  name: 'DeskTopMenuAside',
  data () {
    return {}
  },
  created () {},
  methods: {}
}
</script>

<style scoped>
.desk-top-menu-aside {
  width: 25%;
  box-sizing: border-box;
  font-size: 13px;
}
.desk-top-menu-aside-body {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
  height: 100%;
}
</style>
