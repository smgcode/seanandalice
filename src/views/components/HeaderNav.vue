<template>
<div class="header-nav-container"
  :class="[{
    'is-at-top': scrollAtTop,
   }]">
  <div class="header-nav">
    <a href="#"
      v-scroll-to="'#home'">
    <div class="carabiner">
      <svg version="1.1" id="Calque_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
         viewBox="0 0 45 90">
        <g>
          <g>
            <path class="st0" d="
              M37,62.3c-0.5,1.6-5.6,10-15.5,11.1c-9.9,1.2-15.1-3.1-16.8-6.9c-1.7-3.8-1-6.3,0.1-10.9
              c1.1-4.5,6.1-19.4,9.1-27.6c3-8.2,9.3-10,15-8c5.7,2,10.8,6.3,11.7,15.1c0.2,1.1-1,5.1-1,5.1s-4.3-0.2-4.2-1
              c0.1-0.9,0.5-4.1,0.2-4.7c-0.2-0.7-0.9-0.9-1.1-1.6c-0.1-0.8-3-5.8-5.8-6.8c-2.7-1-7-2.2-8.9,2.3c-1.9,4.5-9.7,29-10.3,31.4
              c-0.6,2.4-0.5,6,3.9,7.2c4.4,1.2,9.5,1,13.3-1.3c3.8-2.4,5.1-5.1,5.5-5.8c0.4-0.7,1.4-3.8,1.4-3.8s1.2-0.8,1.4-0.8
              c0.3,0,1.2,0.1,1.4,
              0.2C36.7,55.6,
              37.3,61.3,
              37,62.3z"/>
            <path class="st2" d="
              M33.6,64.8c0,0-6.6,7.8-16.1,7.4c-10-0.5-13.5-6.5-12.8-11.3c0.7-4.8,2.5-9.3,5.2-17.6
              c2.8-8.3,5.2-18.9,9.3-21.4c4.1-2.5,13.7-2.5,19.1,8.7"/>
            <path class="st2" d="
              M35.9,32.3c-0.3-1.5-1.7-9.7-11.1-10.5c-7.3-0.6-7.9,7-8.2,8.7c-0.4,2.9-2.7,9.3-4.1,13.5
              c-1.4,4.2-3.6,11.2-4.6,13.1c-1,1.9-2.5,4.3-1.1,7.6c1.4,3.3,4.1,5.1,9.2,5.5c5.1,0.3,10.7-0.4,15.3-6.1"/>
          </g>
        </g>
        <g>
          <path class="st0" d="
            M39.5,45l0.4-2.8c0,0-0.3-0.5-0.1-1.8c0.3-1.3,1-4.5,0.7-4.7c-0.3-0.3-1.2-0.8-2.5-0.9
            c-1.3-0.1-2.4,0-2.6,0.3c-0.2,0.4-0.8,4.5-0.9,5c-0.1,0.5-0.6,1.2-0.6,1.2l-0.5,2.6l-2.2,13c0,0-0.5,3.8,0.5,4.1
            c0.9,0.4,4.2,1,4.6,0.7c0.4-0.2,1-2.3,1-2.3s-0.1-1,0.2-2c0.2-1,0.5-0.9,
            0.5-0.9L39.5,45z"/>
          <g>
            <path class="st0 st0--right" d="
              M38.4,58.2c0,0,0.8-0.7,0.9-1.6c0-0.1,0-0.3,0.1-0.5c-0.1-0.1,0-0.4,0.1-0.4c0.4-2.1,1.2-6.8,1.2-7
              c-0.1-0.2-0.1-0.2-0.1-0.2s-0.2-3.1-0.4-3.3c-0.2-0.2-1.6-0.7-3.6-1c-1.9-0.3-3.6-0.4-3.8-0.3c-0.2,0.1-1.3,2.3-1.4,3.1
              c0,0-0.2-0.1-0.3,0.4c-0.1,0.5-1.1,6.7-1.1,6.7c0.2,0.1,0.1,0.3,0,0.3c0,0.6-0.1,2.1,0.2,
              2.3C30.7,57,
              38.4,58.2,
              38.4,58.2z"/>
            <path class="st2" d="
            M40.7,48.7c0,0-2.6-0.9-4.7-1.2c-2.9-0.4-4.5-0.5-4.5-0.5"/>
          </g>
        </g>
        <g>
          <ellipse class="st4" cx="37.9" cy="37.1" rx="0.9" ry="0.9"/>
        </g>
      </svg>
    </div>
    </a>

    <div v-for="navItem in navigation">
      <a href="#"
        v-scroll-to="'#' + navItem.hash">{{ navItem.name }}</a>
    </div>
  </div>
</div>
</template>

<script>
import Vue from 'vue';
import VueScrollTo from 'vue-scrollto';

Vue.use(VueScrollTo, {
  container: 'body',
  duration: 500,
  easing: 'ease-in-out',
  onDone: false,
  onCancel: false,
});

export default {
  name: 'HeaderNav',
  props: [],
  data() {
    return {
      scrollAtTop: true,
      navigation: [{
          name: 'Info',
          hash: 'info',
        },
        {
          name: 'RSVP',
          hash: 'rsvp',
        },
        // {
        //   name: 'Story',
        //   hash: 'story',
        // },
        {
          name: 'Logistics',
          hash: 'logistics',
        },
        {
          name: 'WhosWho',
          hash: 'whoswho',
        },
        {
          name: 'Registry',
          hash: 'registry',
        }],
    };
  },
  methods: {
    checkScrollTop: function checkScrollTop() {
      this.scrollAtTop = (window.scrollY === 0);
    }
  },
  mounted() {
    window.addEventListener('scroll', this.checkScrollTop);
  },
  destroyed() {
    window.removeEventListener('scroll', this.checkScrollTop);
  },
}
</script>

<style lang="scss" scoped>
@import '../../assets/styles/settings.scss';

.st0{fill:#CCC;stroke:#1A171B;stroke-width:0.8;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
.st1{fill:#FFFFFF;stroke:#1A171B;stroke-width:0.8;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
.st2{fill:none;stroke:#1A171B;stroke-width:0.5;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
.st3{fill:#FFFFFF;stroke:#1A171B;stroke-width:0.5;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}
.st4{fill:none;stroke:#1A171B;stroke-width:0.8;stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:10;}

.st0--right {
  fill: #7c52d8;
}

.header-nav-container {
  position: fixed;
  width: 100vw;
  background-color: rgba(50, 50, 50, 0.7);
  z-index: 11;
  transition:
    box-shadow 1s ease-in-out,
    background-color 1s ease-in-out,
    opacity 1s ease-in-out,
    visibility 1s ease-in-out;

  a {
    color: white;
    text-decoration: none;
  }

}


.header-nav {
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 8px;
  font-weight: 500;
  text-transform: uppercase;
  max-width: $container-width;
  margin: 0 auto;
  font-size: 12px;

  @media (min-width: $desktop) {
    font-size: 20px;
  }
}
.carabiner {
  width: 35px;
  height: 50px;
  transform: translateY(-10px);
}
.is-at-top {
  box-shadow: none;
  background-color: rgba(30, 15, 61, 0);
  opacity: 0;
  visibility: hidden;
}
</style>
