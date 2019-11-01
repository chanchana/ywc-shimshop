<template>
  <div class="footer">
    <div class="container">
      <div class="columns">
        <div class="column">
          <p>Copyright © 2003-2019</p>
        </div>
        <div v-for="item in navItems" class="column">
          <a :href="item.href" style="color:white">{{item.label}}</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      navItems: [],
    };
  },
  props: {
    items: Array
  },
  watch: {
    items: function(newVal, oldVal) {
      this.navItems = newVal;
    }
  }
};
</script>

<style scoped>
.footer {
  background-color: #213A8F;
  font-weight: bold;
  color: white;
  font-size: 12px;
  padding: 20px 50px;
}
</style>