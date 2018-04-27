<template>
<div class="hero-container"
:style="`background-image: url('${imageURL}')`">
  <div class="hero"
    :class="[{
      'hero--white': theme === 'white',
      'hero--up': position === 'up',
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
  props: ['imageURL', 'title', 'subtitle', 'theme', 'position'],
}
</script>

<style lang="scss">
@import '../../assets/styles/settings.scss';

.hero-container {
  background-size: cover;
  background-position-y: 40%;
  background-position-x: 50%;
  height: 25vh;
  overflow: hidden;

  @media (min-width: $tablet) {
    height: 33vh;
  }

  @media (min-width: $desktop) {
    height: 50vh;
  }

  transition: filter 1s ease-in-out;

  filter: grayscale(100%);

  &:hover {
    filter: grayscale(0%);
  }
}

.hero {
  color: #333454;
  width: 100vw;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

  .hero--white {
    color: #FFFFFF;
  }

  .hero--up {
    transform: translateY(-25%);
  }

  .hero__title {
    text-shadow: 0 4px 16px 0 rgba(0,0,0,0.26);
    font-weight: 500;
    font-size: 32px;

    @media (min-width: $desktop) {
      font-weight: 600;
      font-size: 48px;
    }

  }

  .hero__subtitle {
    text-shadow: 0 4px 16px 0 rgba(0,0,0,0.26);
    font-size: 16px;

    @media (min-width: $desktop) {
      font-size: 24px;
    }
  }
</style>
