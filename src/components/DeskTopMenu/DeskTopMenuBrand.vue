<template>
  <figure class="desk-top-menu-brand">
    <div
      class="link-div"
      @click="rootMenu.handleItemClick(to)">
      <slot></slot>
    </div>
  </figure>
</template>

<script>
export default {
  name: 'DeskTopMenuBrand',
  inject: ['rootMenu'],
  props: {
    to: {
      default: ''
    }
  }
}
</script>

<style scoped>
.desk-top-menu-brand {
  width: 15%;
  margin: 1em 0;
  box-sizing: border-box;
}
.desk-top-menu-brand > .link-div > img {
  width: 4rem;
  height: 4rem;
  margin-right: 1rem;
}
.desk-top-menu-brand > .link-div {
  font-weight: bold;
  font-size: 1.2rem;
  display: flex;
  align-items: center;
  color: #fff;
}
</style>
