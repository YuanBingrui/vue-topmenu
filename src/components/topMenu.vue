<template>
  <div id="menuBox">
    <div class="logoBox">
      <img v-if="logoImg" :src="logoImg">
    </div>
    <div class="menuBody">
      <ul>
        <li v-for="(menu, index) in menuArr" ref="menuItem" @click="currentMenu(index)" @mouseenter="hover(index)" @mouseleave="leave"><a :href="menu.href">{{menu.name}}</a></li>
      </ul>
      <span ref="slideBox"></span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'topMenu',
  props: {
    primaryColor: {
      type: String,
      default: '#42b983'
    },
    slideSpeed: {
      type: String,
      default: '0.7s'
    },
    logoImg: {
      type: String
    },
    menuArr: {
      validator: (val) => val instanceof Array
    }
  },
  data () {
    return {
      menuIndex: 0,
      leftValue: 0
    }
  },
  mounted: function () {
    console.log(this.slideSpeed)
    this.currentMenu(this.menuIndex)
    if (this.primaryColor) {
      document.getElementById('menuBox').style.setProperty('--primary-color', this.primaryColor)
    }
    if (this.slideSpeed) {
      document.getElementById('menuBox').style.setProperty('--slide-speed', this.slideSpeed)
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
  --primary-color: '';
  --slide-speed: '';
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px var(--primary-color) solid;
  position: sticky;
  padding: 2px 0 10px 0;
}
.logoBox {
  margin-left: 50px;
  display: flex;
  align-items: center;
}
.logoBox img {
  width: 50px;
  height: 50px;
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
  transition:left var(--slide-speed);
  -moz-transition:left var(--slide-speed); /* Firefox 4 */
  -webkit-transition:left var(--slide-speed); /* Safari and Chrome */
  -o-transition:left var(--slide-speed); /* Opera */
}
</style>
