<template>
  <div>
    <div class="columns" style="padding:80px 80px">
      <div v-for="contact in contacts" class="column" style="padding:0px 10px;text-align:center">
        <a :href="contact.href">
          <img class="logo" :src="`contact-logo/${contact.name}.png`">
        </a>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      contacts: [
        {
          name: 'Banner_KTB_SQ',
          href: 'tel:021111144',
        },
        {
          name: 'Banner_CGD_Sq',
          href: 'tel:022706400',
        },
        {
          name: 'Banner_TAT_Hotline_Sq',
          href: 'tel:1672',
        },
      ]
    }
  }
}
</script>