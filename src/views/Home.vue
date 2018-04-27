<template>
  <div class="home"
    :class="[{'home--show-us': showUs}]">

    <div class="teaser-container">
      <div class="teaser">
        <div class="teaser__title margin-bottom-1">
          {{ msg }}
        </div>
        <div class="teaser__blurb margin-bottom-2">
          We're tying the knot
        </div>
        <!-- <img src="./sections/knot.svg"> -->
        <knot/>

      </div>
    </div>

<pre class="padding-ends-4" style="background-color: #EEE; margin: 0;">
  BLOCKED ITEMS:
   * Decide Start Time.
   * Research best response form
   * Create gift registry
   * Profile Photos of wedding party (optional)

  TODO:
   * Create navigation
   * Create map
   * Write short story
   * Animate story
   * Format all copy
   * Update reservation URL with codes

  NAVIGATION:
    Home
    Info
    RSVP
    Story
    Logistics
    Registry
</pre>
    <info/>
    <rsvp/>
    <story/>
    <logistics/>
    <whosWho/>
    <registry/>

  </div>
</template>

<script>
import story from './sections/Story.vue';
import info from './sections/Info.vue';
import rsvp from './sections/RSVP.vue';
import logistics from './sections/Logistics.vue';
import whosWho from './sections/WhosWho.vue';
import registry from './sections/Registry.vue';
import knot from './sections/Knot.vue';


export default {
  name: 'Home',
  components: {
    story,
    info,
    rsvp,
    logistics,
    whosWho,
    registry,
    knot,
  },
  data () {
    return {
      msg: 'Sean & Alice',
      showUs: false,
    }
  },
  mounted() {
    window.setTimeout(() => {
      this.showUs = true;
    }, 100);
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
@import "../assets/styles/spacing.scss";
@import "../assets/styles/settings.scss";


pre {
  font-size: 24px;
  overflow: hidden;
}

.home {
  height: 100vh;
  background: url('./../assets/F01A1952.jpg') no-repeat center center fixed;
  background-size: cover;
  opacity: 0;
  transition: 0.5s opacity ease-in-out;
}

  .home--show-us {
    opacity: 1;
  }

.teaser-container {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  flex-direction: column;
}

.teaser {
  color: white;
  text-shadow: 0 4px 12px rgba(0,0,0,.26);
  text-align: center;
}


  .teaser__title {
    font-size: 50px;
    font-weight: 600;

    @media (min-width: $tablet) {
      font-size: 75px;
    }

    @media (min-width: $desktop) {
      font-size: 100px;
    }
  }

  .teaser__blurb {
    font-size: 25px;
    font-weight: 400;

    @media (min-width: $tablet) {
      font-size: 35px;
    }

    @media (min-width: $desktop) {
      font-size: 50px;
    }
  }

</style>
