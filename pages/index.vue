<template>
  <div class="custom-font">
    <NavBar :items="navItems" text="yay!" />
    <div style="height:64px" />
    <Banner />
    <FeatureButton :duration="duration"/>


    <div class="container">
      <h1>TestJa</h1>res data
      <p>{{resData}}</p>
      <p>{{resData}}</p>
      <p>{{resData}}</p>
      <p>{{resData}}</p>navbaritem
      <p>{{navItems}}</p>
    </div>
  </div>
</template>

<script>
import Logo from "~/components/Logo.vue";
import NavBar from "~/components/NavBar.vue";
import Banner from "~/components/Banner.vue";
import FeatureButton from "~/components/FeatureButton.vue"
import axios from "axios";

export default {
  components: {
    Logo,
    NavBar,
    Banner,
    FeatureButton,
  },
  data() {
    return {
      links: {},
      navItems: [],
      duration: '',
      resData: '',
    };
  },
  methods: {
    fetchData() {
      axios.get("https://panjs.com/ywc.json").then(res => {
        this.resData = res.data
        this.navItems = this.resData.navbarItems
        this.duration = this.resData.duration
      });
    }
  },
  created() {
    this.fetchData();
  }
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Prompt&display=swap');
.custom-font {
  font-family: 'Prompt', sans-serif;
}
</style>