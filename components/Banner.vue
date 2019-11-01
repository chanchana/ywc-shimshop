<template>
  <div class="columns is-gapless is-mobile" style="min-height: 220px; max-height: 350px;overflow: hidden;">
    <div class="column">
      <img class="img-column" src="~/assets/hero-banner/banner-left.png">
    </div>
    <div class="column is-relative">
      <img class="img-column" src="~/assets/hero-banner/banner-center.png">
      
      <figure class="image is-hidden-mobile" style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 240px;">
        <img src="~/assets/logo/banner.png">
      </figure>

      <figure class="image is-hidden-desktop is-hidden-tablet-only" style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 100px;">
        <img src="~/assets/logo/banner.png">
      </figure>
    </div>
    <div class="column">
      <img class="img-column" src="~/assets/hero-banner/banner-right.png">
    </div>
  </div>
</template>

<style scoped>
.img-column {
  width:100%;
  height:100%;
  object-fit: cover;
}
</style>