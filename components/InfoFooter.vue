<template>
  <div class="info-footer">
    <div class="columns">
      <div class="column">
        <img src="~/assets/logo.png" width="108" />
      </div>
      <div v-for="info in infos" class="column">
        <div class="info-title">{{info.title}}</div>
        <div class="info-context" v-html="info.context"/>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      infos: [
        {
          title: 'ข้อมูลลงทะเบียนประชาชน',
          context: 'การรับสิทธิ การใช้งานแอปพลิเคชั่น “เป๋าตัง” และ “ถุงเงิน”<br>ติดต่อ ชิมช้อปใช้ Call Center by Krungthai <a class="nowrap" href="tel:021111144" style="color:#333333">โทร.0 2111 1144</a>'
        },
        {
          title: 'ข้อมูลลงทะเบียนผู้ประกอบการ',
          context: 'เงื่อนไขและวิธีการเข้าร่วมมาตรการฯ<br>ติดต่อ <a class="nowrap" href="tel:022706400" style="color:#333333">โทร.0 2270 6400 กด 7</a>'
        },
        {
          title: 'ข้อมูลเที่ยวชิมช้อปใช้',
          context: 'ติดต่อ ททท.<br><a class="nowrap" href="tel:1672" style="color:#333333">โทร1672</a>'
        },
      ]
    }
  }
};
</script>

<style scoped>
.info-footer {
  background-color: #fafafa;
  color: black;
  font-size: 12px;
  padding: 30px;
}

.info-title {
  font-weight: bold;
  color: #E6332A;
  margin-top: 24px;
  font-size: 16px;
}

.info-context {
  font-size: 14px;
  color: #333333;
}
</style>