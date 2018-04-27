<template>
<div>
  <hero
    title="Registry"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <pre class="padding-ends-4" style="background-color: #EEE; margin: 0;">
        Registry
          BLOCKED: Zola
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
