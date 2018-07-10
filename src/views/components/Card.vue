<template>
<div class="card-container"
  :class="[{
    'card-container--full': isCardFull,
    }]">
  <hero
    :title="name"
    theme="white"
    :small="true"
    :primary="isCardFull"
    :imageURL="imageLink">
  </hero>
  <div class="card">
    <div class="margin-bottom-2">{{ description }}</div>
    <div v-if="url" class="card__cta">
      <a :href="url" target="_blank">
        <button class="button button--cta">{{ name }}</button>
      </a>
    </div>
    <div v-if="isCardFull">
      <chalet></chalet>
    </div>
  </div>
</div>
</template>

<script>
import hero from './Hero.vue';
import chalet from './Chalet.vue';

export default {
  name: 'Card',
  props: ['name', 'description', 'url', 'imageURL', 'isCardFull'],
  components: {
    hero,
    chalet,
  },
  computed: {
    imageLink: function imageLink() {
      const placeholder = 'https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg';
      return (!!this.imageURL) ? this.imageURL : placeholder;
    },
  }
}
</script>

<style lang="scss">
@import '../../assets/styles/settings.scss';


.card {
  background-color: #FFFFFF;
  color: #555555;
  padding: 16px;

  @media (min-width: $tablet) {
    padding: 24px;
  }

  @media (min-width: $desktop) {
    padding: 32px;
  }

  // border-bottom-left-radius: 8px;
  // border-bottom-right-radius: 8px;
}

.card-container {
  border-radius: 8px;
  flex-grow: 1;
  flex-basis: 45%;
}

.card-container--full {
  flex-basis: 100%;
}

.card__cta {
  text-align: center;
}

a {
  text-decoration: none;
}
</style>
