<template>
<div class="hero-container"
  :style="`background-image: url('${imageURL}')`"
  :class="[{
    'hero--small': small,
    'hero--primary': primary,
    'hero--nograyscale': small,
    }]">
  <div v-if="!small" class="hero-border"></div>
  <div class="hero"
    :class="[{
      'hero--white': theme === 'white',
      'hero--up': position === 'up',
      'hero--down': position === 'down',
    }]">
    <div class="hero__title">
      {{ title }}
    </div>
    <div class="hero__subtitle">
      {{ subtitle }}
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: 'Info',
  props: ['imageURL', 'title', 'subtitle', 'theme', 'position', 'small', 'primary'],
}
</script>

<style lang="scss">
@import '../../assets/styles/settings.scss';

.hero-container {
  background-size: cover;
  background-position-y: 50%;
  background-position-x: 50%;
  max-width: $container-width;
  margin: 0 auto;
  height: 25vh;
  overflow: hidden;
  position: relative;

  &.hero--small {
    height: 200px;
  }

  &.hero--small.hero--primary {
    height: 300px;
  }

  @media (min-width: $tablet) {
    height: 40vh;

    &.hero--small {
      height: 200px;
    }

  }

  @media (min-width: $desktop) {
    height: 55vh;

    &.hero--small {
      height: 200px;
    }

  }

  transition: filter 0.5s ease-in-out;

  filter: grayscale(100%);

  &.hero--nograyscale {
    filter: grayscale(0%);
  }

  &:hover {
    filter: grayscale(0%);
  }

}

.hero {
  color: #333454;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  width: calc(100% - 16px * 4);
  margin-left: 32px;
  align-content: center;
  text-align: center;
}

  .hero--white {
    color: #FFFFFF;
  }

  .hero--up {
    // transform: translateY(-25%);
  }

  .hero--down {
    // transform: translateY(25%);
  }

  .hero__title {
    text-shadow: 0 4px 12px rgba(0, 0, 0, 0.6);
    font-weight: 500;
    font-size: 32px;
    font-family: 'Abril Fatface', cursive;
    letter-spacing: 10px;
    text-transform: uppercase;

    @media (min-width: $desktop) {
      font-weight: 600;
      font-size: 64px;
    }

    .hero--small & {
      font-size: 24px;
    }

  }

  .hero__subtitle {
    text-shadow: 0 4px 12px rgba(0, 0, 0, 0.6);
    font-size: 16px;

    @media (min-width: $desktop) {
      font-size: 24px;
    }
  }

  $border-width: 2px;
  $border-offset: 16px;
  .hero-border {
    border: double $border-width rgba(255, 255, 255, 0.3);
    top: $border-offset;
    left: $border-offset;
    width: calc(100% - (16px * 2 + 2px));
    height: calc(100% - (16px * 2 + 2px));
    position: absolute;
  }


</style>
