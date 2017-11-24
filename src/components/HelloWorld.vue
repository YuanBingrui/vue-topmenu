<template>
  <div class="menuBox">
    <ul>
      <li v-for="(menu, index) in menuArr"  @click="currentMenu(index)" ref="menuItem"><a href="#">{{menu.value}}</a></li>
    </ul>
    <span></span>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      menuArr: [{name: 'menu01', value: 'Core Docs'}, {name: 'menu02', value: 'Forum'}, {name: 'menu03', value: 'Community'},
      {name: 'menu04', value: 'Twitter'}, {name: 'menu05', value: 'Vue Router'}, {name: 'menu06', value: 'Vuex'}]
    }
  },
  methods: {
    currentMenu: function (index) {
      console.log(this.$refs.menuItem[index])
    }
  }
}
</script>

<style scoped>
.menuBox {
  width: 100%;
  padding: 2px 0 10px 0;
  border-bottom: 1px rgba(66,185,131,0.4) solid;
  position: sticky;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
  width: 120px;
  text-align: center;
}
a {
  text-decoration: none;
  color: #42b983;
  padding: 20px 10px;
}
span {
  border-bottom: 5px #42b983 solid;
  width: 120px;
  position: absolute;
  left: 0;
}
</style>
