<template>
  <div class="top-menu-brand">
    <a :href="href">
      <slot>Brand</slot>
    </a>
  </div>
</template>

<script>
export default {
  name: 'TopMenuBrand',
  props: {
    href: {
      type: String,
      default: ''
    }
  }
}
</script>

<style scoped>
.top-menu-brand {
  margin-left: 3rem;
  margin-right: 1.5rem;
}
.top-menu-brand img {
  width: 4rem;
  height: 4rem;
  margin-right: 1rem;
}
.top-menu-brand a {
  text-decoration: none;
  font-weight: bold;
  font-size: 1.2rem;
  display: flex;
  align-items: center;
}
</style>
