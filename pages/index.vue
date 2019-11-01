<template>
  <div>
    <NavBar :items="navItems" text="yay!" />
    <div class="container">
      <h1>TestJa</h1>
      res data
      <p>{{resData}}</p>
      navbaritem
      <p>{{navItems}}</p>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import NavBar from "~/components/NavBar.vue";
import axios from "axios";

export default {
  components: {
    Logo,
    NavBar
  },
  data() {
    return {
      links: {},
      navItems: [],
      resData: ""
    };
  },
  methods: {
    fetchData() {
      axios.get("https://panjs.com/ywc.json").then(res => {
        this.resData = res.data
        this.navItems = this.resData.navbarItems
      })
    }
  },
  created() {
    this.fetchData();
  }
};
</script>