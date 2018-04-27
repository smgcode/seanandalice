<template>
<div>
  <hero
    title="Who's who"
    subtitle="Wedding party & parents"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <pre class="padding-ends-4" style="background-color: #EEE; margin: 0;">
    Who's who
      Wedding Party
        Bride: Alice Hsu
        Groom: Sean Gee
        Maid of Honor: Katharine Pan
        Best Man: Alex Lee
        Bridesmaid: Yvonne Yip
        Groomsman: Johnny Yip
        Bridesmaid: Jean Hsu
        Groomsman: Steve Sin
        Jr. Bridesmaid: Ariel Bigelow-Gee
      Parents
        Wing & Tina Gee
        Jerry and Sharon Hsu
  </pre>
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
