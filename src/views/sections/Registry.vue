<template>
<div class="bottom">
  <hero
    title="Registry"
    theme="white"
    :imageURL="imageURL">
  </hero>

  <div class="content-container">
    <div class="section-border"></div>
    <div class="section section--center">

      <div class="section__item">
        <div class="registries">
          <div v-for="registry in registries" class="registry padding-1">
            <div class="registry__image margin-bottom-2">
              <img :src="registry.image">
            </div>
            <a :href="registry.url" target="_blank">
              <button class="button button--registry">
                {{ registry.title }}
              </button>
            </a>
          </div>
        </div>
      </div>

    </div>
  </div>

</div>
</template>

<script>
import hero from '../components/Hero.vue';
import constants from '../constants.js';

const imageURL = constants.heros.registry;

export default {
  name: 'Info',
  components: {
    hero,
  },
  data() {
    return {
      imageURL,
      registries: constants.registries,
    };
  },
}
</script>

<style lang="scss">
@import "../../assets/styles/settings.scss";

.temp {
  text-align: left;
}

a {
  color: white;
}

.registries {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

$image-size: 200px;

@media (min-width: $tablet) {
  $image-size: 20px;
}

@media (min-width: $desktop) {
  $image-size: 2px;
}

.registry {
  padding: 16px;
}

.registry a {
  display: flex;
  flex-direction: column;
  align-items: center;
}
  .registry__image {
    display: flex;
    align-items: center;
    background: white;
    width: $image-size;
    height: $image-size;

    img {
      width: $image-size;
    }
  }

.button--registry {
  width: $image-size;
}

.bottom {
  padding-bottom: 64px;

  @media (min-width: $tablet) {
    padding-bottom: 92px;
  }

  @media (min-width: $desktop) {
    padding-bottom: 128px;
  }
}

</style>
