<template>
  <li class="top-menu-item">
    <a :href="href">
      <slot></slot>
    </a>
  </li>
</template>

<script>
export default {
  name: 'TopMenuItem',
  props: {
    href: {
      type: String,
      default: ''
    }
  },
  data () {
    return {}
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped>
.top-menu-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  margin: 0;
  list-style: none;
}
.top-menu-item > a {
  text-decoration: none;
  padding: 1.1rem 0.7rem;
  text-align: center;
  margin: 0 0.7rem;
  color: #6b6b6b;
}
</style>
