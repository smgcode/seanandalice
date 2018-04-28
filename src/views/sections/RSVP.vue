<template>
<div>
  <hero
    title="RSVP"
    subtitle="We hope you can make it"
    position="down"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524379217/273A3833.jpg">
  </hero>
  <div class="content-container padding-ends-4">
    <div class="section__item">
      <div class="section__item__title">
        Kindly reply by September 7th 2018
      </div>
      <div>[ ] Accepts with pleasure</div>
      <div class="margin-bottom-2">[ ] Declines with regret</div>
      <div>Please let us know if you have any food restrictions.</div>
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
