<template>
  <header
    class="menu-container menu-container-sm menu-container-md menu-container-lg"
    ref="menuContainer">
    <desk-top-menu v-bind="$attrs"/>
    <mobile-top-menu v-bind="$attrs"/>
  </header>
</template>

<script>
import DeskTopMenu from './DeskTopMenu/DeskTopMenu'
import MobileTopMenu from './MobileTopMenu/MobileTopMenu'
import * as Headroom from 'headroom.js'

export default {
  name: 'TopMenu',
  components: {
    DeskTopMenu,
    MobileTopMenu
  },
  props: {
    primaryColor: {
      type: String,
      default: '#38b48b'
    }
  },
  data () {
    return {
      activeIndex: '0_nav'
    }
  },
  provide () {
    return {
      rootMenu: this
    }
  },
  mounted () {
    this.$nextTick(function () {
      this.bindScrollerFn()
      if (this.primaryColor) {
        this.$refs.menuContainer.style.setProperty('--primary-color', this.primaryColor)
      }
    })
  },
  methods: {
    handleItemClick (to) {
      if (to) {
        this.routeToItem(to, (error) => {
          if (error) console.error(error)
        })
      }
    },
    routeToItem (to, onError) {
      let route = to
      try {
        this.$router.push(route, () => {}, onError)
      } catch (e) {
        console.error(e)
      }
    },
    bindScrollerFn () {
      let topMenuElement = document.querySelector('header')
      let headroom = new Headroom(topMenuElement,
        {
          'offset': 200,
          'tolerance': 0,
          'classes': {
            'initial': 'animated',
            'pinned': 'slideDown',
            'unpinned': 'slideUp'
          }
        })
      headroom.init()
    }
  }
}
</script>

<style>
.menu-container {
  --primary-color: '';
  width: 100%;
  background: var(--primary-color);
  position: fixed;
  z-index: 10;
  right: 0;
  left: 0;
  top: 0;
}
@media (min-width: 1200px) {
  .menu-container-lg {
    height: 100px;
  }
}
@media (min-width: 768.01px) and (max-width: 1199.98px) {
  .menu-container-md {
    height: 100px;
  }
}
@media (max-width: 768px) {
  .menu-container-sm {
    height: 70px;
  }
}
.animated {
  animation-duration: 0.5s;
  animation-fill-mode: both;
  will-change: transform, opacity;
}
@-webkit-keyframes slideDown {
  0% {
    -webkit-transform: translateY(-100%);
  }
  100% {
    -webkit-transform: translateY(0);
  }
}
@-moz-keyframes slideDown {
  0% {
    -moz-transform: translateY(-100%);
  }
  100% {
    -moz-transform: translateY(0);
  }
}

@-o-keyframes slideDown {
  0% {
    -o-transform: translateY(-100%);
  }
  100% {
    -o-transform: translateY(0);
  }
}

@keyframes slideDown {
  0% {
    transform: translateY(-100%);
  }
  100% {
    transform: translateY(0);
  }
}
.animated.slideDown {
  animation-name: slideDown;
}
@-webkit-keyframes slideUp {
  0% {
    -webkit-transform: translateY(0);
  }
  100% {
    -webkit-transform: translateY(-100%);
  }
}
@-moz-keyframes slideUp {
  0% {
    -moz-transform: translateY(0);
  }
  100% {
    -moz-transform: translateY(-100%);
  }
}
@-o-keyframes slideUp {
  0% {
    -o-transform: translateY(0);
  }
  100% {
    -o-transform: translateY(-100%);
  }
}
@keyframes slideUp {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(-100%);
  }
}
.animated.slideUp {
  animation-name: slideUp;
}
</style>
