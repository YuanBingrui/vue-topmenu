<template>
  <figure class="mobile-top-menu-brand">
    <div
      class="link-div"
      @click="rootMenu.handleItemClick(to)">
      <slot></slot>
    </div>
  </figure>
</template>

<script>
export default {
  name: 'MobileTopMenuBrand',
  inject: ['rootMenu'],
  props: {
    to: {
      default: ''
    }
  }
}
</script>

<style scoped>
.mobile-top-menu-brand {
  width: 60%;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 0;
  box-sizing: border-box;
  height: 100%;
}
.mobile-top-menu-brand > .link-div > img {
  width: 2rem;
  height: 2rem;
  margin-right: 0.7rem;
}
.mobile-top-menu-brand > .link-div {
  font-weight: bold;
  font-size: 1.2rem;
  display: flex;
  align-items: center;
  color: #6b6b6b;
}
</style>
