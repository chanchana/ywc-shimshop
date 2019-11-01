<template>
  <div class="feature-box">
    <p>ตั้งแต่วันที่</p>
    <!-- Desktop -->
    <h1 class="feature-duration is-hidden-mobile">{{durationText}}</h1>
    <!-- Mobile -->
    <h1 class="feature-duration is-hidden-desktop is-hidden-tablet-only" style="font-size: 28px;">{{durationText}}</h1>
    
    <div style="position:relative">
      <a :href="buttonHref">
        <!-- Desktop -->
        <div class="feature-button is-hidden-mobile"><span v-html="buttonText"></span></div>
        <!-- Mobile -->
        <div class="feature-button is-hidden-desktop is-hidden-tablet-only" style="font-size: 14px; width:90%"><span v-html="buttonText"></span></div>
      </a>
      <!-- Backgrounf line -->
      <div class="is-hidden-mobile" style="width: 98%; background-color: grey; height: 1px; position: absolute; top: 80%; left: 50%; transform: translate(-50%, -50%); z-index: -1; opacity: 0.3;"></div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      durationText: 'Loading...',
      buttonText: 'ลงทะเบียน เฟส 2<br>ตั้งแต่วันที่ 24 ต.ค.62 วันละ 2 รอบ <span class="nowrap">เวลา 6.00 และ 18.00 น.</span><br>(จำกัดจำนวนผู้ลงทะเบียนรอบละ 5 แสนคน <span class="nowrap">รวม 1 ล้านคนต่อวัน)</span>',
      buttonHref: 'https://regist.ชิมช้อปใช้.com/Register/',
    }
  },
  props: {
    duration: String,
  },
  watch: {
    duration: function(newVal, oldVal) {
      this.durationText = newVal;
    }
  }
}
</script>

<style scoped>
.feature-box {
  text-align: center;
  margin: 26px 0px;
  font-weight: bold;
}
.feature-duration {
  font-size: 48px;
  color: #E6332A;
  font-weight: 900;
}
.feature-button {
  color: #fff;
  border-radius: 5px;
  box-shadow: 0 15px 30px 0 rgba(28, 78, 132, 0.4);
  background-color: #213A8F;
  font-size: 24px;
  margin: 10px auto;
  width: 80%;
  max-width: 900px;
  padding: 10px;
  transition: 0.3s;
}
.feature-button:hover {
  background-color: #FABB43;
  box-shadow: 0 15px 30px 0 rgba(250, 187, 67, 0.4);
  color: white;
}
</style>