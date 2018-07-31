<template>
  <nav class="mobile-top-menu-nav">
    <ul class="mobile-top-menu-nav-body">
      <slot></slot>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'MobileTopMenuNav',
  data () {
    return {}
  },
  created () {},
  methods: {}
}
</script>

<style scoped>
.mobile-top-menu-nav {}
.mobile-top-menu-nav-body {
  width: 100%;
  padding: 10px 0 10px 30px;
  margin: 0;
  list-style: none;
}
</style>
