<template>
  <nav class="top-menu-nav">
    <ul class="top-menu-nav-body">
      <slot></slot>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'TopMenuNav',
  data () {
    return {}
  },
  created () {},
  methods: {}
}
</script>

<style scoped>
.top-menu-nav {
  width: 60%;
  box-sizing: border-box;
  display: flex;
  justify-content: center;
}
.top-menu-nav-body {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
}
.top-menu-nav-body > li:last-child {
  padding-right: 0;
}
</style>
