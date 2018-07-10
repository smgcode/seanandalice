<template>
<div>
  <hero
    title="Logistics"
    subtitle="How to get there & what to do"
    theme="white"
    :imageURL="imageURL">
  </hero>

  <div class="content-container">
    <div class="section-border"></div>
    <div class="section section--left padding-ends-2 padding-top-4">

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Directions
      </div>

      <div class="section__item section__item--center margin-bottom-2">
        500 Dodge Ridge Rd, Pinecrest, CA 95364
      </div>
      <div class="section__item section__item--center margin-bottom-3">
        <a :href="getDirectionsURL" target="_blank">
          <button class="button">
            Get directions
          </button>
        </a>
      </div>


      <div class="margin-bottom-4" id="map"></div>

      <div class="section__item margin-bottom-3">
        <div class="section__item--secondary" >
          Driving From the Bay Area:
        </div>
        <ul>
          <li v-for="direction in directions.bay" class="padding-bottom-1">
            {{ direction }}
          </li>
        </ul>
      </div>

      <div class="section__item margin-bottom-3">
        <div class="section__item--secondary" >
          Driving From Southern California
        </div>
        <ul>
          <li v-for="direction in directions.socal" class="padding-bottom-1">
            {{ direction }}
          </li>
        </ul>
      </div>

      <div class="section__item margin-bottom-3">
        <div class="section__item--secondary">
          Airports
        </div>
        <ul>
          <li v-for="airport in directions.airports" class="padding-bottom-1">
            {{ airport }}
          </li>
        </ul>
      </div>

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Lodging
      </div>
      <div class="section__item padding-bottom-4">
        <div class="cards">
          <card v-for="lodge in lodging"
            :key="lodge.name"
            class="margin-bottom-2 padding-1"
            :name="lodge.name"
            :isCardFull="lodge.isCardFull"
            :description="lodge.description"
            :imageURL="lodge.image"
            :url="lodge.url">
          </card>
        </div>
      </div>

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Local Activities
      </div>
      <div class="section__item margin-bottom-4">
        <div class="activities">
          <div v-for="activity in activities"
            class="activity padding-2 margin-bottom-1">
            <div class="activity__icon">
              <img :src="activity.icon">
            </div>
            <div class="activity__title margin-bottom-2">
              {{ activity.title }}
            </div>
            <a v-for="activityItem in activity.urls"
              :href="activityItem.url"
              target="_blank"
              class="activity__link margin-bottom-1">
              <div class="activity__link__title padding-1">
                {{ activityItem.title }}
              </div>
            </a>

          </div>
        </div>
      </div>

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Local Restaurants &amp; Stores
      </div>
      <div class="section__item margin-bottom-4">
        <div class="activities">
          <div v-for="business in businesses"
            class="activity padding-2 margin-bottom-1">
            <div class="activity__icon">
              <img :src="business.icon">
            </div>
            <div class="activity__title margin-bottom-2">
              {{ business.title }}
            </div>
            <a v-for="businessItem in business.urls"
              :href="businessItem.url"
              target="_blank"
              class="activity__link margin-bottom-1">
              <div class="activity__link__title padding-1">
                {{ businessItem.title }}
              </div>
            </a>

          </div>
        </div>
      </div>

      <div class="section__item section__item--primary section__item--center margin-bottom-2">
        Nearby towns
      </div>
      <div class="section__item margin-bottom-4">
        <div class="activities">
          <div v-for="town in towns"
            class="activity padding-2 margin-bottom-1">
            <div class="activity__icon">
              <img :src="town.icon">
            </div>
            <div class="activity__title margin-bottom-2">
              {{ town.title }}
            </div>
            <a v-for="townItem in town.urls"
              :href="townItem.url"
              target="_blank"
              class="activity__link margin-bottom-1">
              <div class="activity__link__title padding-1">
                {{ townItem.title }}
              </div>
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
import card from '../components/Card.vue';
import styles from './mapStyles.json';
import constants from '../constants.js';

import trees from '../../assets/icons/trees.svg';
import carabiner from '../../assets/icons/carabiner.svg';
import hiking from '../../assets/icons/hiking.svg';
import kayak from '../../assets/icons/kayak.svg';
import saddle from '../../assets/icons/saddle.svg';
import coffeeShop from '../../assets/icons/coffee-shop.svg';
import grocery from '../../assets/icons/grocery.svg';
import park from '../../assets/icons/park.svg';



const imageURL = constants.heros.logistics;


export default {
  name: 'Info',
  components: {
    hero,
    card,
  },
  data() {
    return {
      map: null,
      imageURL,
      towns: [
        {
          name: 'sonora',
          title: 'Sonora (30 mi)',
          urls: [
            {
              url: 'https://www.sonoraca.com/visit-sonora/',
              title: 'Visit Sonora',
            },
          ],
          icon: park,
        },
        {
          name: 'jamestown',
          title: 'Jamestown (32 mi)',
          urls: [
            {
              url: 'https://historicjamestowne.org/visit/plan-your-visit/visitor-center/',
              title: 'Visit Jamestown',
            },
          ],
          icon: trees,
        },
      ],
      businesses: [
        {
          name: 'pinecrest',
          title: 'Pinecrest',
          urls: [
            {
              url: 'https://www.yelp.com/biz/strawberry-inn-restaurant-strawberry',
              title: 'Strawberry Inn Restaurant',
            },
            {
              url: 'https://goo.gl/maps/CKoDLsLX4BN2',
              title: 'Pinecrest General Store',
            },
            {
              url: 'https://www.yelp.com/biz/the-serene-bean-pinecrest',
              title: 'The Serene Bean',
            },
            {
              url: 'https://www.yelp.com/biz/the-steam-donkey-pinecrest',
              title: 'The Steam Donkey',
            },
            {
              url: 'https://www.yelp.com/biz/mias-cold-springs',
              title: 'Mia’s',
            },
          ],
          icon: grocery,
        },
        {
          name: 'twainharte',
          title: 'Twain harte (19 mi)',
          urls: [
            {
              url: 'https://www.yelp.com/biz/the-rock-of-twain-harte-twain-harte',
              title: 'The Rock of Twain Harte',
            },
            {
              url: 'https://www.yelp.com/biz/twain-harte-market-twain-harte-2',
              title: 'Twain Harte Market',
            },
            {
              url: 'https://www.yelp.com/biz/alicias-sugar-shack-twain-harte-4',
              title: 'Alicia’s Sugar Shack',
            },
            {
              url: 'https://www.yelp.com/biz/caffe-blossom-twain-harte',
              title: 'Caffe’ Blossom',
            },
            {
              url: 'https://www.yelp.com/biz/cibo-famiglia-twain-harte',
              title: 'CiBO Famiglia',
            },
          ],
          icon: coffeeShop,
        },
      ],
      activities: [
        {
          name: 'hiking',
          title: 'Hiking',
          urls: [
            {
              url: 'https://www.alltrails.com/trail/us/california/cleos-bath-trail',
              title: 'Cleos Bath Trail',
            },
            {
              url: 'https://www.alltrails.com/trail/us/california/pinecrest-peak-trail',
              title: 'Pinecrest Peak Trail',
            },
            {
              url: 'https://www.alltrails.com/trail/us/california/pinecrest-lake-loop',
              title: 'Pinecrest Lake Loop',
            },
          ],
          icon: hiking,
        },
        {
          name: 'kayaking',
          title: 'Water Sports',
          urls: [
            {
              url: 'http://pinecrestlakeresort.com/pinecrest-marina.html',
              title: 'Pinecrest Marina',
            }],
          icon: kayak,
        },
        {
          name: 'horseback',
          title: 'Horseback Riding',
          urls: [
            {
              url: 'http://www.aspenmeadowpackstation.com/',
              title: 'Aspen Meadows Packstation',
            }],
          icon: saddle,
        },
        {
          name: 'climbing',
          title: 'Climbing',
          urls: [
            {
              url: 'https://www.mountainproject.com/area/107299550/sonora-pass-highway-108',
              title: 'Sonora Pass',
            }],
          icon: carabiner,
        },
      ],
      lodging: {
        pinecrestChalet: {
          name: 'Pinecrest Chalet',
          description: 'The wedding will be held in the Pinecrest Chalet Amphitheatre. If you would like to book accommodations at Pinecrest Chalet please contact Sean and he will help book your accommodation. We have blocked off the entire venue. Friday and Saturday night stay required.',
          isCardFull: true,
          // url: constants.links.bookings.pinecrestChalet,
          image: constants.links.image.pinecrestChalet,
        },
        mccaffreyHouse: {
          name: 'McCaffrey House B&B',
          description: 'We found this lovely bed and breakfast that is on the way to Pinecrest Chalet that is about 25 minutes away. We have the the rooms blocked off until August 29th. To make reservations please call and let them know you are attending Hsu-Gee wedding as their online reservations are closed for this event.',
          url: constants.links.bookings.mccaffreyHouse,
          image: constants.links.image.mccaffreyHouse,
        },
        pinecrestResort: {
          name: 'Pinecrest Resort',
          description: 'The Pinecrest Resort is only 5 minutes away and manages the marina by the lake. They have a restaurant called the Steamed Donkey and a general store nearby.',
          url: constants.links.bookings.pinecrestResort,
          image: constants.links.image.pinecrestResort,
        },
        strawberryInn: {
          name: 'Strawberry Inn',
          description: 'Strawberry Inn is also 5 minutes away and has it\'s own restaurant and the Stanislaus river behind it.',
          url: constants.links.bookings.strawberryInn,
          image: constants.links.image.strawberryInn,
        },
        airBnB: {
          name: 'AirBnB',
          description: 'Along the 108 you can find some rentals with AirBnB. You can expand the search down to Sonora which is about a 40 minute drive to the venue.',
          url: constants.links.bookings.airBnB,
          image: constants.links.image.airBnB,
        },
      },
      getDirectionsURL: 'https://goo.gl/maps/ZitTvUPdn8n',
      directions: {
        bay: [
          'Head east on 580 towards Livermore',
          'Around Tracy, take the 205 freeway east',
          'From the 205, take the 120 freeway east towards Escalon and Oakdale',
          'From the 120, take the 108 and follow signs to Sonora',
          'Stay on 108, and go about 30 miles up the mountain from Sonora, following signs to Pinecrest',
          'From 108, veer right onto Pinecrest Lake Rd. for about 1/2 mile',
          'Turn right onto Dodge Ridge Rd. for about 3/4 mile',
          'Turn right at the Pinecrest Chalet entrance—look for the big bear!',
        ],
        socal: [
          'Take I-5 North to 99 North (a few miles past Grapevine)',
          'Stay on 99 North to 59 North (at Merced, be careful not to take 59 South)',
          'Follow 59 North signs through Merced for a couple of miles',
          'From 59 North turn left on J59 aka La Grange Rd., about a mile past Snelling',
          'From J59 turn right / East on 108 / 120—well past Don Pedro Reservoir',
          'Stay on 108, and follow signs to Pinecrest, about 30 miles past Sonora up the mountain',
          'From 108, veer right onto Pinecrest Lake Rd. for about 1/2 mile',
          'Turn right onto Dodge Ridge Rd. for about 3/4 mile',
          'Turn right at the Pinecrest Chalet entrance—look for the big bear!',
        ],
        airports: [
          'Oakland (144 miles)',
          'Sacramento (146 miles)',
          'Fresno (148 miles)',
          'San Francisco (163 miles)',
        ],
      },
    };
  },
  mounted() {
    this.initMap();
  },
  methods: {
    initMap: function initMap() {
      this.map = new window.google.maps.Map(document.getElementById('map'), {
        center: {lat: 38.184817, lng: -119.992660},
        zoom: 8,
        mapTypeId: 'terrain',
        styles,
      });
      window.setTimeout(() => {
        new google.maps.Marker({
          position: {lat: 38.184817, lng: -119.992660},
          map: this.map,
          animation: google.maps.Animation.DROP,
        })
      }, 500);
    },
  },
}
</script>

<style lang="scss">
#map {
  height: 25vh;
  width: 100%;
}
.cards {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.activities {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

  .activity {
    text-align: center;
  }

    .activity__title {
    }

    .activity__link {
      font-size: 16px;
      color: #FFFFFF;
      text-decoration: underline;

      .activity__link__title {
        transition: opacity 0.3s ease-in-out;

        &:hover,
        &:focus,
        &:active {
          opacity: 0.7;
        }

      }



    }

    .activity__icon {
      img {
        color: white;
        width: 50px;
        fill: white;
      }

      svg {
        fill: #FFFFFF;
      }
    }

.color-white {
  color: #FFFFFF;
}
</style>
