<template>
  <li class="top-sub-menu-container">
    <span class="top-sub-menu-title">
      <slot name="title"></slot><i class="iconfont icon-arrow-down"></i>
    </span>
    <ul class="top-sub-menu-body">
      <slot></slot>
    </ul>
  </li>
</template>

<script>
export default {
  name: 'TopSubMenu',
  data () {
    return {}
  },
  created () {},
  mounted () {},
  methods: {}
}
</script>

<style scoped>
/*.top-sub-menu {
  flex-grow: 2;
}*/
@font-face {
  font-family: "iconfont";
  src: url('../../assets/font/iconfont.eot'); /* IE9*/
  src: url('../../assets/font/iconfont.eot#iefix') format('embedded-opentype'), /* IE6-IE8 */
  url('data:application/x-font-woff;charset=utf-8;base64,d09GRgABAAAAAAUAAAsAAAAAB1QAAQAAAAAAAAAAAAAAAAAAAAAAAAAAAABHU1VCAAABCAAAADMAAABCsP6z7U9TLzIAAAE8AAAARAAAAFZW7kiQY21hcAAAAYAAAABeAAABhpvQBr5nbHlmAAAB4AAAAS0AAAE84MmNsWhlYWQAAAMQAAAALwAAADYR+PHSaGhlYQAAA0AAAAAcAAAAJAfeA4RobXR4AAADXAAAAAwAAAAMC+kAAGxvY2EAAANoAAAACAAAAAgAdgCebWF4cAAAA3AAAAAfAAAAIAESAF1uYW1lAAADkAAAAUUAAAJtPlT+fXBvc3QAAATYAAAAJwAAADhRU1DueJxjYGRgYOBikGPQYWB0cfMJYeBgYGGAAJAMY05meiJQDMoDyrGAaQ4gZoOIAgCKIwNPAHicY2Bk/sE4gYGVgYOpk+kMAwNDP4RmfM1gxMjBwMDEwMrMgBUEpLmmMDgwVDxbxtzwv4EhhrmBoQEozAiSAwAvrg0SeJzFkMENgDAMAy9t6QMxCA8G4sUcnaijdY1iQnkwQS05VhxLiQIsQBQPMYFdGA9OueZ+ZHU/eSZLjUBptXf1nyqiWXYNKplpsHmr/9i87qPTVyiDOrHVl4Qb+14OJwAAeJwVj71Kw1AARu93Y25yY5vYm/+0MU1iG6UaMMaKiO3iYnEQnBx1V3Dq4tBFcBDxGUTwIayzTr6D6OBTROPhcPZDZEJ+P6W55BGTrJJNckCOCQEbINFpiDgrczqAHcu2a+lSlmaxkia5tA83YZZTDMu+yxRmQMcytuJimOU0w3Y5onsonBDw28GJ6HWE9ADNy5Zvqgl9hB2lHWO0UR2uj62ia6rThhC+EHcqk2WV0gVDx4XrcJlrrHqSjcCeR2s0QsPPgqPTZrctzm7Ly7DncmA2g9nu6s/jVtCqvQ4cU/jKUlP1gma6YmH6veiZjbD/RWrwH+mHvtSvpOcUOxjmYApYkiGvF1x8hJMO7jm1fF5dqZZanXPfAn8NI7xpvqBatcs53jUIXyN/wAsvyAAAAHicY2BkYGAA4udhNR7x/DZfGbhZGEDges61dwj6/0MWBmYJIJeDgQkkCgBP9wvJAHicY2BkYGBu+N/AEMPCAAJAkpEBFTADAEcJAmwEAAAAA+kAAAQAAAAAAAAAAHYAnnicY2BkYGBgZghkYGUAASYg5gJCBob/YD4DABD3AXAAeJxlj01OwzAQhV/6B6QSqqhgh+QFYgEo/RGrblhUavdddN+mTpsqiSPHrdQDcB6OwAk4AtyAO/BIJ5s2lsffvHljTwDc4Acejt8t95E9XDI7cg0XuBeuU38QbpBfhJto41W4Rf1N2MczpsJtdGF5g9e4YvaEd2EPHXwI13CNT+E69S/hBvlbuIk7/Aq30PHqwj7mXle4jUcv9sdWL5xeqeVBxaHJIpM5v4KZXu+Sha3S6pxrW8QmU4OgX0lTnWlb3VPs10PnIhVZk6oJqzpJjMqt2erQBRvn8lGvF4kehCblWGP+tsYCjnEFhSUOjDFCGGSIyujoO1Vm9K+xQ8Jee1Y9zed0WxTU/3OFAQL0z1xTurLSeTpPgT1fG1J1dCtuy56UNJFezUkSskJe1rZUQuoBNmVXjhF6XNGJPyhnSP8ACVpuyAAAAHicY2BigAAuBuyAmZGJkZmRhYGxgiuxqCi/PD4lvzyPgQEAKowE4QA=') format('woff'),
  url('../../assets/font/iconfont.ttf') format('truetype'), /* chrome, firefox, opera, Safari, Android, iOS 4.2+*/
  url('../../assets/font/iconfont.svg#iconfont') format('svg'); /* iOS 4.1- */
}
.iconfont {
  font-family:"iconfont" !important;
  font-size: 16px;
  font-style: normal;
  margin-left: 5px;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.icon-arrow-down:before { 
  content: "\e6a6";
  /*transition: .3s;*/
}
/*.icon-arrow-down:before:hover {
  transform: rotateZ(180deg)
}*/
.top-sub-menu-container, .top-sub-menu-body {
  list-style-type: none;
  padding: 1.1rem 0.7rem;
  text-align: center;
  margin: 0 0.7rem;
  cursor: pointer;
}
.top-sub-menu-container {
  transition: .3s;
}
/*.top-sub-menu-title {
  transition: .3s;
}*/
.top-sub-menu-container:hover .top-sub-menu-title{
  transform: rotateZ(180deg)
}
.top-sub-menu-body {
  display: none;
}
.top-right {
  flex-grow: 0.5;
}
.top-right ul {
  text-align: right;
  padding-right: 2rem;
}
</style>
