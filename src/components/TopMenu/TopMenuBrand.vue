<template>
  <figure class="top-menu-brand">
    <a :href="href">
      <slot></slot>
    </a>
  </figure>
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
  width: 15%;
  margin: 1em 0;
  box-sizing: border-box;
}
.top-menu-brand img {
  width: 4rem;
  height: 4rem;
  margin-right: 1rem;
}
.top-menu-brand > a {
  text-decoration: none;
  font-weight: bold;
  font-size: 1.2rem;
  display: flex;
  align-items: center;
  color: #6b6b6b;
}
</style>
