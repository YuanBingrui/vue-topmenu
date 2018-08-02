<template>
  <li class="mobile-top-sub-menu-container" @click="toggleExpand">
    <span class="mobile-top-sub-menu-title">
      <slot name="mobile-title"></slot>
      <svg aria-hidden="true" class="icon-arrow-down" ref="iconArrowDown" viewBox="0 0 16 16" xmlns="http://www.w3.org/2000/svg" width="16" height="16" role="img">
        <path d="M.447 13.044c.554.554 1.46.554 2.015 0L8.01 6.362l5.548 6.682c.554.554 1.46.554 2.014 0 .554-.554.554-1.46 0-2.015l-6.48-7.62c-.295-.293-.69-.426-1.082-.407-.39-.02-.784.114-1.082.408l-6.48 7.616c-.555.554-.555 1.46 0 2.018z""></path>
      </svg>
    </span>
    <div class="mobile-top-sub-menu-content" ref="mobileSubMenuBody">
      <ul class="mobile-top-sub-menu-body">
        <slot></slot>
      </ul>
    </div>
  </li>
</template>

<script>
export default {
  name: 'MobileTopSubMenu',
  props: {
    subMenuNum: {
      type: Number,
      default: 0
    }
  },
  data () {
    return {
      isExpand: false
    }
  },
  created () {},
  mounted () {
    this.removeStyle(this.$refs.mobileSubMenuBody, this.$refs.iconArrowDown)
  },
  methods: {
    toggleExpand () {
      if (this.isExpand) {
        this.removeStyle(this.$refs.mobileSubMenuBody, this.$refs.iconArrowDown)
        this.isExpand = false
      } else {
        this.addStyle(this.$refs.mobileSubMenuBody, this.$refs.iconArrowDown)
        this.isExpand = true
      }
    },
    addStyle (el, iconEl) {
      el.style.height = this.subMenuNum * 57 + 'px'
      el.style.transform = 'scale(1, 1)'
      el.style.transformOrigin = '0 0'
      iconEl.style.transform = 'rotateZ(360deg)'
    },
    removeStyle (el, iconEl) {
      el.style.height = '0'
      el.style.transform = 'scale(1, 0)'
      iconEl.style.transform = 'rotateZ(180deg)'
    }
  }
}
</script>

<style scoped>
.mobile-top-sub-menu-container {
  list-style: none;
  color: #6b6b6b;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  align-items: center;
  border-top: 1px solid #000;
  position: relative;
}
.mobile-top-sub-menu-title {
  width: 100%;
  text-align: left;
  padding: 18px 0;
}
.mobile-top-sub-menu-title .icon-arrow-down {
  width: 16px;
  height: 12px;
  fill: #6b6b6b;
  transition: transform .3s;
}
.mobile-top-sub-menu-container .icon-arrow-down {
  transform: rotateZ(180deg)
}
.mobile-top-sub-menu-content {
  color: #6b6b6b;
  background: #f8f4e6;
  border: none;
  width: 100%;
  transition: transform .3s, height .3s;
  text-align: left;
  height: 0;
}
.mobile-top-sub-menu-body {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  padding-left: 7px;
}
.mobile-top-sub-menu-body > li {
  color: #6b6b6b;
  list-style: none;
  width: 100%;
}
</style>
