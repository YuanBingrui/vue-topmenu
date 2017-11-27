<template>
  <div id="menuBox">
    <div class="menuBody">
      <ul>
        <li v-for="(menu, index) in menuData.menuArr" ref="menuItem" @click="currentMenu(index)" @mouseenter="hover(index)" @mouseleave="leave"><a href="#">{{menu.value}}</a></li>
      </ul>
      <span ref="slideBox"></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'topMenu',
  props: ['menuData'],
  data () {
    return {
      primaryColor: '',
      menuIndex: 0,
      leftValue: 0
    }
  },
  mounted: function () {
    this.currentMenu(this.menuIndex)
    if (this.menuData.primaryColor) {
      document.getElementById('menuBox').style.setProperty('--primary-color', this.menuData.primaryColor)
    }
  },
  methods: {
    currentMenu: function (index) {
      this.menuIndex = index
      this.hover(index)
    },
    hover: function (index) {
      this.getLeftValue(index)
      this.$refs.slideBox.style.width = this.$refs.menuItem[index].getBoundingClientRect().width + 'px'
      this.$refs.slideBox.style.left = this.leftValue + 'px'
    },
    leave: function () {
      this.getLeftValue(this.menuIndex)
      this.$refs.slideBox.style.width = this.$refs.menuItem[this.menuIndex].getBoundingClientRect().width + 'px'
      this.$refs.slideBox.style.left = this.leftValue + 'px'
    },
    getLeftValue: function (index) {
      this.leftValue = 0
      for (let i = 0; i < index; i++) {
        this.leftValue = this.leftValue + this.$refs.menuItem[i].getBoundingClientRect().width
      }
    }
  }
}
</script>

<style scoped>
#menuBox {
  --primary-color: #42b983;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  border-bottom: 1px var(--primary-color) solid;
  position: sticky;
  padding: 2px 0 10px 0;
}
.menuBody {
  position: relative;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  transition: width 2s ease 1s;
  -moz-transition: width 2s ease 1s; /* Firefox 4 */
  -webkit-transition: width 2s ease 1s; /* Safari and Chrome */
  -o-transition: width 2s ease 1s; /* Opera */
}
a {
  text-decoration: none;
  color: var(--primary-color);
  padding: 20px 10px;
  text-align: center;
  margin: 0 10px;
}
span {
  height: 5px;
  background-color: var(--primary-color);
  border-radius: 2.5px;
  position: absolute;
  transition:left 1s;
  -moz-transition:left 1s; /* Firefox 4 */
  -webkit-transition:left 1s; /* Safari and Chrome */
  -o-transition:left 1s; /* Opera */
}

</style>
