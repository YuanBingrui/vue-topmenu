<template>
  <li class="desk-top-sub-menu-container">
    <span class="desk-top-sub-menu-title">
      <slot name="title"></slot>
      <svg aria-hidden="true" class="icon-arrow-down" viewBox="0 0 16 16" version="1.1" xmlns="http://www.w3.org/2000/svg" width="16" height="16" role="img"><path d="M.447 13.044c.554.554 1.46.554 2.015 0L8.01 6.362l5.548 6.682c.554.554 1.46.554 2.014 0 .554-.554.554-1.46 0-2.015l-6.48-7.62c-.295-.293-.69-.426-1.082-.407-.39-.02-.784.114-1.082.408l-6.48 7.616c-.555.554-.555 1.46 0 2.018z""></path></svg>
    </span>
    <div class="desk-top-sub-menu-content">
      <ul class="desk-top-sub-menu-body">
        <slot></slot>
      </ul>
    </div>
  </li>
</template>

<script>
export default {
  name: 'DeskTopSubMenu',
  data () {
    return {}
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped>
.desk-top-sub-menu-container {
  list-style: none;
  padding-right: 2rem;
  cursor: pointer;
  color: #6b6b6b;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.desk-top-sub-menu-title .icon-arrow-down {
  width: 16px;
  height: 12px;
  fill: #6b6b6b;
  transition: .3s;
}
.desk-top-sub-menu-container .icon-arrow-down {
  transform: rotateZ(180deg)
}
.desk-top-sub-menu-container:hover .icon-arrow-down {
  transform: rotateZ(360deg)
}
.desk-top-sub-menu-content {
  color: #6b6b6b;
  background: #fbfcfd;
  position: absolute;
  top: 101%;
  left: 0;
  width: 100%;
  height: 0;
  border: none;
  overflow: hidden;
  transition: height .4s;
  text-align: center;
}
.desk-top-sub-menu-body {
  list-style-type: none;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  box-sizing: border-box;
}
.desk-top-sub-menu-body > li {
  display: flex;
  color: #6b6b6b;
  list-style: none;
}
.desk-top-sub-menu-container:hover .desk-top-sub-menu-content {
  height: 90px;
  border-bottom: 1px solid #d4d6d6;
}
</style>
