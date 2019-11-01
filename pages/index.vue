<template>
  <div class="custom-font">
    <NavBar :items="navItems" />
    <div style="height:64px" />
    <Banner />
    <FeatureButton :duration="duration" />
    <div class="container">
      <!-- Content -->
      <div style="padding:30px 70px">
        <!-- Title -->
        <!-- Desktop -->
        <div class="content-title is-hidden-mobile" v-html="titleText" />
        <!-- Mobile -->
        <div class="content-title is-hidden-desktop is-hidden-tablet-only" v-html="titleText" style="font-size: 24px" />
        <!-- Detail -->
        <div v-html="detailText" class="content-detail" />
        
        <!-- Condition -->
        <div class="content-detail">
          <strong>เงื่อนไขการเข้าร่วมมาตรการ</strong>
          <div v-html="conditionText" style="padding: 10px 0px 0px 0px"/>
        </div>
      </div>
      <!-- EndContent -->
      <ContactInfo />
      <BrandLogo />
    </div>
    <InfoFooter />
    <Footer :items="navItems" />
  </div>
</template>

<script>
import NavBar from "~/components/NavBar.vue"
import Banner from "~/components/Banner.vue"
import FeatureButton from "~/components/FeatureButton.vue"
import ContactInfo from "~/components/ContactInfo.vue"
import BrandLogo from "~/components/BrandLogo.vue"
import InfoFooter from "~/components/InfoFooter.vue"
import Footer from "~/components/Footer.vue"
import axios from "axios"

export default {
  components: {
    NavBar,
    Banner,
    FeatureButton,
    ContactInfo,
    BrandLogo,
    InfoFooter,
    Footer,
  },
  data() {
    return {
      links: {},
      navItems: [],
      duration: '',
      titleText: 'มาตรการส่งเสริมการบริโภค<br>ในประเทศ <span class="nowrap">“ชิมช้อปใช้”</span>',
      detailText: 'Loading',
      conditionText: 'Loading',
      resData: '',
    };
  },
  methods: {
    fetchData() {
      axios.get("https://panjs.com/ywc.json").then(res => {
        this.resData = res.data
        this.navItems = this.resData.navbarItems
        this.duration = this.resData.duration
        this.detailText = this.resData.detail
        this.conditionText = this.resData.condition
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
.content-title {
  font-size: 36px;
  font-weight: 900;
  color: #E6332A;
}
.content-detail {
  font-size: 18px;
  color: #333333;
  padding: 28px 0px 0px 0px;
}
</style>