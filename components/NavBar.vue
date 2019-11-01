<template>
  <div class="columns">
    <div class="column" />
    <div v-for="item in navItems" class="column is-2">
      <a v-if="item" class="button is-fullwidth is-white" :href="item.href">{{item.label}}</a>
    </div>
    <div class="column" />
  </div>
</template>

<script>
export default {
  data () {
    return {
      navItems: [],
      ready: false
    }
  },
  props: {
    items: Array,
    text: String,
  },
  watch: { 
    items: function(newVal, oldVal) {
      this.navItems = newVal
    }
  }
}
</script>