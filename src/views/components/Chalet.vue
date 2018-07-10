<template>
<div class="margin-top-3">
  To see the Pinecrest Chalet accommodations please visit <a :href="accommodations" target="_blank">here</a> and to see their site layout please visit <a :href="map" target="_blank">here</a>
</div>
</template>

<script>
export default {
  name: 'Chalet',
  props: [''],
  data() {
    return {
      accommodations: 'https://alumni.berkeley.edu/travel/pinecrest-chalet/planning-your-trip/accommodations',
      map: 'https://alumni.berkeley.edu/sites/default/files/Chalet_RV_site.pdf',
    };
  },
  computed: {
  }
}
</script>

<style lang="scss" scoped>
// @import '../../assets/styles/settings.scss';
@import '../../assets/styles/spacing.scss';

a {
  color: #23415E;
  text-decoration: underline;
}
</style>
