<template>
<div>
  <hero
    title="Who's who"
    subtitle="Wedding party & parents"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <div class="content-container padding-ends-4">
    <div class="section__item">
      <div class="section__item__title">
        Wedding Party
      </div>
      <pre>
Bride: Alice Hsu
Groom: Sean Gee
Maid of Honor: Katharine Pan
Best Man: Alex Lee
Bridesmaid: Yvonne Yip
Groomsman: Johnny Yip
Bridesmaid: Jean Hsu
Groomsman: Steve Sin
Jr. Bridesmaid: Ariel Bigelow-Gee
      </pre>
      <div class="section__item__title">
        Parents
      </div>
      <div>
        Wing & Tina Gee
      </div>
      <div>
        Jerry and Sharon Hsu
      </div>
    </div>
  </div>
</div>
</template>

<script>
import hero from '../components/Hero.vue';

export default {
  name: 'Info',
  components: {
    hero,
  },
}
</script>

<style>
</style>
