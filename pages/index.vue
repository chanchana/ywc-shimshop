<template>
  <div class="custom-font">
    <NavBar :items="navItems" />
    <div style="height:64px" />
    <Banner />
    <FeatureButton :duration="duration" />

    <BrandLogo />
    <InfoFooter />
    <Footer :items="navItems" />
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
import Logo from "~/components/Logo.vue"
import NavBar from "~/components/NavBar.vue"
import Banner from "~/components/Banner.vue"
import FeatureButton from "~/components/FeatureButton.vue"
import BrandLogo from "~/components/BrandLogo.vue"
import InfoFooter from "~/components/InfoFooter.vue"
import Footer from "~/components/Footer.vue"
import axios from "axios"

export default {
  components: {
    Logo,
    NavBar,
    Banner,
    FeatureButton,
    BrandLogo,
    InfoFooter,
    Footer,
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

<style>
@import url('https://fonts.googleapis.com/css?family=Prompt&display=swap');
.custom-font {
  font-family: 'Prompt', sans-serif;
}
.nowrap {
  white-space: nowrap;
}
</style>