<template>
<div>
  <hero
    title="Registry"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <div class="content-container padding-ends-4">
    <div class="section__item">
      <div class="section__item__title">
        Zola
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
