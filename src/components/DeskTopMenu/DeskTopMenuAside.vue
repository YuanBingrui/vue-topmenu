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
@media (min-width: 1200px) {
  .desk-top-menu-aside {
    width: 30%;
    height: 100%;
    box-sizing: border-box;
    font-size: 13px;
  }
}
@media (min-width: 768.01px) and (max-width: 1199.98px) {
  .desk-top-menu-aside {
    width: 100%;
    box-sizing: border-box;
    font-size: 13px;
    height: 50%;
    display: flex;
    justify-content: flex-end;
  }
}
.desk-top-menu-aside-body {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
  height: 100%;
}
.desk-top-menu-aside-body > li:last-child {
  padding-right: 0;
}
</style>
