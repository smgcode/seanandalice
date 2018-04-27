<template>
<div>
  <hero
    title="Information"
    subtitle="Where to go and when to be there"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <pre class="padding-ends-4" style="background-color: #EEE; margin: 0;">
    Info
      Date:
        9/29/2018
      Time:
        BLOCKED: (3:00PM)
      Address:
        Pinecrest Chalet
        500 Dodge Ridge Rd, Pinecrest, CA 95364
      Dress code
        Cocktail Attire
        Please note this is an outdoor wedding and will continue into the evening.
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
