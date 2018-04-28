<template>
<div>
  <hero
    title="Information"
    subtitle="Where to go and when to be there"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <div class="content-container padding-ends-4">
    <div class="temp">
      BLOCKED ITEMS:
        <ul>
          <li v-for="block in blocked">
            {{ block }}
          </li>
        </ul>
      TODO:
      <ul>
        <li v-for="todo in todos">
          {{ todo }}
        </li>
      </ul>
    </div>

    <div class="section__item" v-for="(infoValue, infoKey) in info">
      <div class="section__item__title">
        {{ infoKey }}:
      </div>
      <div>
        {{ infoValue }}
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
  data() {
    return {
      blocked: [
        'Decide Start Time.',
        'Research best response form',
        'Create gift registry',
        'Profile Photos of wedding party (optional)'
      ],
      todos: [
        'Create navigation',
        'Create map',
        'Write short story',
        'Animate story',
        'Format all copy',
        'Update reservation URL with codes'
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

</style>
