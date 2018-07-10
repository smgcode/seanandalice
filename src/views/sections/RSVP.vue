<template>
<div>
  <hero
    title="RSVP"
    subtitle="We hope you can make it"
    position="down"
    theme="white"
    :imageURL="imageURL">
  </hero>
  <div class="content-container">
    <div class="section-border"></div>
    <div class="section section--center padding-ends-5">
      <div class="section__item">
        Kindly reply by:
      </div>
      <div class="section__item section__item--primary margin-bottom-3" style="color: #AAAAAA;">
        August 10<span style="vertical-align: super; font-size: 30px">th</span> 2018
      </div>
      <div class="section__item">
        We hope you can make it. Please note that dinner will be served buffet style. Vegetarian meals will be provided separate from the buffet. Please contact us direclty if you have any food allergies.
      </div>
      <div class="section__item">
        <iframe id="RSVPifyIFrame"
          style="width:100%; border:none;"
          allowtransparency="true"
          onload="iFrameResize({
            autoResize: true,
            checkOrigin: false,
            heightCalculationMethod: 'max',
            enablePublicMethods: true },
            '#RSVPifyIFrame');"
          src="https://seanandalice.app.rsvpify.com/?embed=1&js=1"
          frameborder="0"
          scrolling="no">
        </iframe>
      </div>
      <div class="section__item subtext padding-1">
        You can alternatively visit
        <a class="rsvp__link"
          href="https://seanandalice.rsvpify.com"
          target="_blank">here</a>
        to RSVP.
      </div>

    </div>
  </div>
</div>
</template>

<script>
import hero from '../components/Hero.vue';
import constants from '../constants.js';
import iframeResize from 'iframe-resizer';

const imageURL = constants.heros.rsvp;

export default {
  name: 'Info',
  components: {
    hero,
  },
  data() {
    return {
      imageURL,
    };
  },
  mounted() {
    window.iFrameResize = iFrameResize;
  },

}
</script>

<style lang="scss">
.sticky_footer {
  opacity: 0;
}

.rsvp__link {
  text-decoration: underline;
  transition: opacity 0.3s ease-in-out;

  &:hover,
  &:focus,
  &:active {
    opacity: 0.7;
  }

}
</style>
