<template>
  <div>
    <!-- Desktop -->
    <div class="is-hidden-mobile columns" style="padding:70px 60px">
      <div v-for="logo in logos" class="column" style="padding:30px;text-align:center">
        <a :href="logo.href">
          <img class="logo" :src="`brand-logo/${logo.name}.png`" style=" max-height:120px">
        </a>
      </div>
    </div>

    <!-- Mobile -->
    <div class="is-hidden-desktop is-hidden-tablet-only" style="padding:70px 30px">
      <div v-for="i in [0, 1]" class="columns is-mobile" style="margin:0px">
        <div v-for="logo in logos.slice(0 + (i * 3), 3 + (i * 3))" class="column is-4" style="padding:0px 24px">
          <a :href="logo.href">
            <img class="logo" :src="`brand-logo/${logo.name}.png`">
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      logos: [
        {
          name: 'MOF',
          href: 'https://www.mof.go.th/th/home',
        },
        {
          name: 'FPO',
          href: 'http://www.fpo.go.th/',
        },
        {
          name: 'CGD',
          href: 'https://www.cgd.go.th/',
        },
        {
          name: 'Krungthai',
          href: 'https://www.newcb.ktb.co.th/',
        },
        {
          name: 'MOTS',
          href: 'https://www.mots.go.th/',
        },
        {
          name: 'TAT',
          href: 'https://thai.tourismthailand.org/',
        },
      ]
    }
  }
}
</script>

<style scoped>
.logo {
  transition: all .5s ease-in-out;
}
.logo:hover {
  transform: scale(1.5);
}
</style>