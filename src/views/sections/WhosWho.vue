<template>
<div>
  <hero
    title="Who's who"
    subtitle="Wedding party & parents"
    theme="white"
    :imageURL="imageURL">
  </hero>
  <div class="content-container">
    <div class="section-border"></div>
    <div class="section section--center padding-ends-2 padding-ends-4">

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Wedding Party
      </div>

      <div class="section__item people-container">

        <div class="people">
          <div v-for="person in bridalParty"
            class="person padding-1">
            <div class="person__title">{{ person.title }}:</div>
            <div class="person__name">{{ person.name }}</div>
          </div>
        </div>

        <div class="people">
          <div v-for="person in groomParty"
            class="person padding-1">
            <div class="person__title">{{ person.title }}:</div>
            <div class="person__name">{{ person.name }}</div>
          </div>
        </div>

        <div class="people">
          <div v-for="person in weddingParty"
            class="person padding-1">
            <div class="person__title">{{ person.title }}:</div>
            <div class="person__name">{{ person.name }}</div>
          </div>
        </div>

      </div>

      <div class="section__item section__item--primary section__item--center margin-bottom-2 margin-top-2">
        Parents
      </div>
      <div class="section__item people-container">
        <div class="people">
          <div v-for="person in family"
            class="person padding-1">
            <div class="person__title">{{ person.title }}:</div>
            <div class="person__name">{{ person.name }}</div>
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

const imageURL = constants.heros.whoswho;

export default {
  name: 'Info',
  components: {
    hero,
  },
  data() {
    return {
      imageURL,
      bridalParty: [
        {
          title: 'Bride',
          name: 'Alice Hsu',
        },
        {
          title: 'Maid of Honor',
          name: 'Katharine Pan',
        },
        {
          title: 'Bridesmaid',
          name: 'Yvonne Yip',
        },
        {
          title: 'Bridesmaid',
          name: 'Jean Hsu',
        },
        {
          title: 'Jr. Bridesmaid',
          name: 'Ariel Bigelow-Gee',
        },
      ],
      groomParty: [
        {
          title: 'Groom',
          name: 'Sean Gee',
        },
        {
          title: 'Best Man',
          name: 'Alex Lee',
        },
        {
          title: 'Groomsman',
          name: 'Johnny Yip',
        },
        {
          title: 'Groomsman',
          name: 'Steve Sin',
        },
      ],
      weddingParty: [
        {
          title: 'Officiant',
          name: 'Wai Ha Ng',
        },
        {
          title: 'Reader',
          name: 'Yue Pui Chin',
        }
      ],
      family: [
        {
          title: 'Groom\'s parents',
          name: 'Wing & Tina Gee',
        },
        {
          title: 'Bride\'s parents',
          name: 'Jerry & Sharon Hsu',
        }
      ],
    };
  },
}
</script>

<style lang="scss">
@import "../../assets/styles/settings.scss";
.people-container {
  display: flex;
  flex-wrap: wrap;

}

.people {
  display: flex;
  flex-wrap: wrap;
  flex-grow: 1;
  flex-basis: 100%;
  flex-direction: column;
  margin-bottom: 16px;
  justify-content: flex-start;

  @media (min-width: $tablet) {
    flex-basis: 50%;
  }

  @media (min-width: $desktop) {
  }
}

.person {
  display: flex;
  flex-wrap: wrap;

  width: 100%;
}

  .person__title {
    flex-basis: 50%;
    opacity: 0.5;
    text-align: right;
  }

  $personal-space: 8px;
  .person__name {
    padding-left: $personal-space;
    flex-basis: calc(50% - $personal-space);
    text-align: left;
  }
</style>
