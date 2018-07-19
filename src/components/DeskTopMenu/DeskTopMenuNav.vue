<template>
  <nav class="desk-top-menu-nav">
    <ul class="desk-top-menu-nav-body">
      <slot></slot>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'DeskTopMenuNav',
  data () {
    return {}
  },
  created () {},
  methods: {}
}
</script>

<style scoped>
.desk-top-menu-nav {
  width: 60%;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
}
.desk-top-menu-nav-body {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
}
.desk-top-menu-nav-body > li:last-child {
  padding-right: 0;
}
</style>
