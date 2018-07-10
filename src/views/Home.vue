<template>
  <div class="home"
    :class="[{'home--show-only-login': !pwValid}]">
    <transition name="fade" mode="out-in">
      <headerNav v-if="pwValid"></headerNav>
    </transition>

    <div id='home' class="teaser-container">
      <transition name="fade" mode="out-in">
        <div v-if="pwValid" class="background-us background-us--show">
        </div>
      </transition>
      <transition name="fade" mode="out-in">
        <div v-if="!pwValid" class="background-us background-us--radial"></div>
      </transition>
      <div class="teaser"
        :class="[{ 'teaser--ontop': pwValid }]">
        <div class="teaser__title margin-bottom-1">
          {{ msg }}
        </div>
        <div class="teaser__blurb margin-bottom-2"
          :class="[{'teaser__blurb--show': showUs}]">
          We're tying the knot
        </div>
        <div class="margin-bottom-2 padding-1" style="height: 30px;">
          <transition name="fade" mode="out-in">
            <div v-if="pwValid" key="valid" class="teaser__scrolldown">
              Scroll Down
            </div>
            <div v-else key="invalid">
              <input v-model="pw" class="pw" type="text" placeholder="Check invite for password">
            </div>
          </transition>
        </div>

        <knot/>

      </div>
    </div>

    <info id='info'/>
    <rsvp id='rsvp'/>
    <!-- <story id='story'/> -->
    <logistics id='logistics'/>
    <whosWho id='whoswho'/>
    <registry id='registry'/>

  </div>
</template>

<script>
// import VueScrollTo from 'vue-scrollto';
import story from './sections/Story.vue';
import info from './sections/Info.vue';
import rsvp from './sections/RSVP.vue';
import logistics from './sections/Logistics.vue';
import whosWho from './sections/WhosWho.vue';
import registry from './sections/Registry.vue';
import knot from './sections/Knot.vue';
import headerNav from './components/HeaderNav.vue';

var keys = {37: 1, 38: 1, 39: 1, 40: 1};

function preventDefault(e) {
  e = e || window.event;
  if (e.preventDefault)
      e.preventDefault();
  e.returnValue = false;
}

function preventDefaultForScrollKeys(e) {
    if (keys[e.keyCode]) {
        preventDefault(e);
        return false;
    }
}

function disableScroll() {
  if (window.addEventListener) // older FF
      window.addEventListener('DOMMouseScroll', preventDefault, false);
  window.onwheel = preventDefault; // modern standard
  window.onmousewheel = document.onmousewheel = preventDefault; // older browsers, IE
  window.ontouchmove  = preventDefault; // mobile
  document.onkeydown  = preventDefaultForScrollKeys;
}

function enableScroll() {
    if (window.removeEventListener)
        window.removeEventListener('DOMMouseScroll', preventDefault, false);
    window.onmousewheel = document.onmousewheel = null;
    window.onwheel = null;
    window.ontouchmove = null;
    document.onkeydown = null;
}

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
    headerNav,
  },
  data () {
    return {
      msg: 'Sean & Alice',
      showUs: false,
      pw: '',
      pwValid: false,
    }
  },
  watch: {
    pw: function pw(newPw, oldPw) {
      if (newPw.toLowerCase() === '#hsupergeewedding' || newPw.toLowerCase() === 'hsupergeewedding') {
        enableScroll();
        this.pwValid = true;
      }
    }
  },
  mounted() {
    window.setTimeout(() => {
      this.showUs = true;
      disableScroll();
    }, 100);
    disableScroll();
  },
}
</script>

<style lang="scss">
@import "../assets/styles/spacing.scss";
@import "../assets/styles/settings.scss";


pre {
  font-size: 24px;
  overflow: hidden;
}

#story,
#rsvp,
#logistics,
#whoswho,
#registry,
#info {
  background-color: #DFDBE5;
  background-image: url("data:image/svg+xml,%3Csvg width='6' height='6' viewBox='0 0 6 6' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='%239C92AC' fill-opacity='0.4' fill-rule='evenodd'%3E%3Cpath d='M5 0h1L0 6V5zM6 5v1H5z'/%3E%3C/g%3E%3C/svg%3E");
  color: #D1C09C;
  padding-top: 64px;

  @media (min-width: $tablet) {
    padding-top: 92px;
  }

  @media (min-width: $desktop) {
    padding-top: 128px;
  }
}
.home {
  height: 100vh;
}



.teaser-container {
  position: relative;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  align-content: center;
  flex-direction: column;
}
.background-us {
  position: absolute;
  transition: 0.5s opacity ease-in-out;
  height: 100%;
  width: 100%;
}
  .background-us--show {
    background: url('./../assets/F01A1952.jpg') no-repeat center center;
    background-size: cover;
    transition: 0.5s background ease-in-out;
  }

  .background-us--radial {
    background: radial-gradient(rgba(0, 0, 0, 0) 60%, rgba(0, 0, 0, 0.13));
    transition: 0.5s background ease-in-out;
  }

.teaser {
  position: absolute;
  color: #CCCCCC;
  text-shadow: 1px 1px 2px rgba(0,0,0,0.7);
  text-align: center;
  font-family: 'Abril Fatface', cursive;
  letter-spacing: 5px;
}

  .teaser--ontop {
    text-shadow: 0 4px 12px rgba(0,0,0,.26);
    color: #FFFFFF;
    transition: 0.5s opacity ease-in-out;
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
    opacity: 0;
    transition: 0.5s opacity ease-in-out;

    @media (min-width: $tablet) {
      font-size: 35px;
    }

    @media (min-width: $desktop) {
      font-size: 50px;
    }
  }

    .teaser__blurb--show {
      opacity: 1;
    }

  .teaser__scrolldown {
    font-size: 20px;
    font-weight: 400;

    @media (min-width: $tablet) {
      font-size: 25px;
    }

    @media (min-width: $desktop) {
      font-size: 30px;
    }
  }

.pw {
  padding: 8px;
  border: solid 1px #CCCCCC;
  border-radius: 4px;
  width: 200px;
  font-size: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);

  &:active,
  &:focus {
    outline: none;
  }
}

$fade-time: 1s;
.fade-enter-active, .fade-leave-active{
  opacity: 1;
  transition: opacity $fade-time;
}
.fade-enter, .fade-leave-to {
  opacity: 0;
  transition: opacity $fade-time;
}

.home--show-only-login {
  overflow: hidden;
}
</style>
