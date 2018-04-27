<template>
<div>
  <hero
    title="RSVP"
    subtitle="We hope you can make it"
    position="down"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524379217/273A3833.jpg">
  </hero>
  <pre class="padding-ends-4" style="background-color: #EEE; margin: 0;">
    RSVP
      Required: named people
        BLOCKED: Need research on how to get people's responses.
      Optional: Food restrictions: "Please let us know if you have any food restrictions."
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
