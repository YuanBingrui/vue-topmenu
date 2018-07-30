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
@media (min-width: 1200px) {
  .desk-top-menu-nav {
    width: 70%;
    box-sizing: border-box;
    display: flex;
    justify-content: center;
    height: 100%;
  }
}
@media (min-width: 768.01px) and (max-width: 1199.98px) {
  .desk-top-menu-nav {
    width: 100%;
    box-sizing: border-box;
    display: flex;
    justify-content: flex-end;
    height: 50%;
  }
}
.desk-top-menu-nav-body {
  display: flex;
  align-items: center;
  padding: 0 1rem;
  margin: 0;
  height: 100%;
}
.desk-top-menu-nav-body > li:last-child {
  padding-right: 0;
}
</style>
