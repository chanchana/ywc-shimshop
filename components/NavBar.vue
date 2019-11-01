<template>
  <div>
    <!-- Desktop -->
    <div class="is-hidden-mobile nav-shadow " style="position:fixed; width:100%;text-align: center;background-color:white;z-index:10;height:64px">
      <a v-for="item in navItems" :href="item.href" class="link hvr-underline-from-center">
        {{item.label}}
      </a>
    </div>

    <!-- Mobile -->
    <nav class="navbar nav-shadow is-fixed-top is-hidden-desktop is-hidden-tablet-only" role="navigation" aria-label="main navigation" style="height:64px;">
      <div class="navbar-brand">
        <a style="height:64px;padding:8px 16px;">
          <img src="logo/logo.png" style="height:48px;" />
        </a>

        <a v-on:click="onClickMenu" role="button" :class="`navbar-burger ${menuClassActive}`" aria-label="menu" aria-expanded="true" style="height:64px;">
          <span aria-hidden="false"></span>
          <span aria-hidden="false"></span>
          <span aria-hidden="false"></span>
        </a>
      </div>

      <div :class="`navbar-menu ${menuClassActive}`" >
        <a v-for="item in navItems" class="navbar-item has-text-right" :href="item.href">
          {{item.label}}
        </a>
      </div>
    </nav>
  </div>

</template>

<script>
export default {
  data() {
    return {
      navItems: [],
      menuIsActive: false,
    };
  },
  props: {
    items: Array,
  },
  computed: {
    menuClassActive: function() {
      if (this.menuIsActive) {
        return 'is-active'
      } else {
        return ''
      }
    }
  },
  watch: {
    items: function(newVal, oldVal) {
      this.navItems = newVal;
    }
  },
  methods: {
    onClickMenu() {
      this.menuIsActive = !this.menuIsActive
    }
  }
};
</script>

<style scoped>
.nav-shadow {
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.1), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.link {
  display: inline-block;
  margin: 20px;
  font-size: 15px;
}

/* Underline From Center */
.hvr-underline-from-center {
  display: inline-block;
  vertical-align: middle;
  -webkit-transform: perspective(1px) translateZ(0);
  transform: perspective(1px) translateZ(0);
  box-shadow: 0 0 1px rgba(0, 0, 0, 0);
  position: relative;
  overflow: hidden;
  color: black;
}
.hvr-underline-from-center:before {
  content: "";
  position: absolute;
  z-index: -1;
  left: 51%;
  right: 51%;
  bottom: 0;
  background: #213A8F;
  height: 4px;
  -webkit-transition-property: left, right;
  transition-property: left, right;
  -webkit-transition-duration: 0.3s;
  transition-duration: 0.3s;
  -webkit-transition-timing-function: ease-out;
  transition-timing-function: ease-out;
}
.hvr-underline-from-center:hover:before,
.hvr-underline-from-center:focus:before,
.hvr-underline-from-center:active:before {
  left: 0;
  right: 0;
}
</style>