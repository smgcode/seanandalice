<template>
<div>
  <hero
    title="Information"
    subtitle="Where to go and when to be there"
    position="up"
    theme="white"
    :imageURL="imageURL">
  </hero>
  <div class="content-container">
    <div class="section-border">
    </div>
    <div class="section section--center padding-ends-5">
      <div class="section__item">
        Please join us on
      </div>
      <div class="section__item section__item--primary">
        September 29<span style="vertical-align: super; font-size: 30px">th</span> 2018
      </div>
      <div class="section__item section__item--secondary margin-bottom-4">
        3:30 PM
      </div>
      <div class="section__item">
        at the
      </div>
      <div class="section__item section__item--primary">
        Pinecrest Chalet
      </div>
      <div class="section__item section__item--secondary margin-bottom-4">
        500 Dodge Ridge Rd,<br> Pinecrest, CA 95364
      </div>

      <div class="section__item margin-bottom-3">
        Festivities will be held outdoors in the amphitheater surrounded by evergreens with the Toulumne creek flowing behind it. Under the night sky temperatures can reach down to the mid 40's (°F).<br>Dress code is cocktail attire
      </div>

      <div class="section__item section__item--primary margin-bottom-1">
        Schedule
      </div>
      <div class="section__item padding-bottom-1">
        <div class="schedule-container">
          <div class="schedule">
            <div class="margin-bottom-2">
              3:30 pm Ceremony
            </div>
            <div class="margin-bottom-2">
              4:00 pm Cocktail Hour
            </div>
            <div class="margin-bottom-2">
              5:00 pm Reception
            </div>
            <div class="margin-bottom-2">
              7:00 pm Dancing
            </div>
          </div>
        </div>
        <div class="subtext padding-1 margin-bottom-1">
          * Please arrive early as the Ceremony will start promptly.
        </div>
      </div>

    </div>
  </div>
</div>
</template>

<script>
import hero from '../components/Hero.vue';
import constants from '../constants.js';

const imageURL = constants.heros.info;

export default {
  name: 'Info',
  components: {
    hero,
  },
  data() {
    return {
      imageURL,
      blocked: [
        'Research best response form',
        'Create gift registry',
        'Decide Start Time.',
        'Profile Photos of wedding party (optional)',
      ],
      todos: [
        'Format all copy',
        'Update reservation URL with codes',
        'Write short story',
        'Animate story',
      ],
      info: {
        date: 'September 29th 2018',
        time: '3:00PM',
        venue: 'Pinecrest Chalet',
        address: '500 Dodge Ridge Rd, Pinecrest, CA 95364',
        dressCode: 'Cocktail Attire',
        note: 'Please note this is an outdoor wedding and will continue into the evening.',
      },
    }
  }
}
</script>

<style lang="scss">
@import "../../assets/styles/settings.scss";
@import "../../assets/styles/base.scss";
.schedule-container {
  max-width: max-content;
  margin: 0 auto;
}

.schedule {
  text-align: left;
}

</style>
