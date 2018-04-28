<template>
<div>
  <hero
    title="Logistics"
    subtitle="How to get there & what is around"
    position="up"
    theme="white"
    imageURL="https://res.cloudinary.com/seangee/image/upload/w_1440/v1524374180/273A4086.jpg">
  </hero>
  <div class="content-container padding-ends-4">
    <div class="section__item">
      <div class="section__item__title">
        Driving From the Bay Area:
      </div>
      <pre>
Head east on 580 towards Livermore
Around Tracy, take the 205 freeway east
From the 205, take the 120 freeway east towards Escalon and Oakdale
From the 120, take the 108 and follow signs to Sonora
Stay on 108, and go about 30 miles up the mountain from Sonora, following signs to Pinecrest
From 108, veer right onto Pinecrest Lake Rd. for about 1/2 mile
Turn right onto Dodge Ridge Rd. for about 3/4 mile
Turn right at the Pinecrest Chalet entrance—look for the big bear!
      </pre>

      <div class="section__item__title">
        Driving From Southern California
      </div>
      <pre>
Take I-5 North to 99 North (a few miles past Grapevine)
Stay on 99 North to 59 North (at Merced, be careful not to take 59 South)
Follow 59 North signs through Merced for a couple of miles
From 59 North turn left on J59 aka La Grange Rd., about a mile past Snelling
From J59 turn right / East on 108 / 120—well past Don Pedro Reservoir
Stay on 108, and follow signs to Pinecrest, about 30 miles past Sonora up the mountain
From 108, veer right onto Pinecrest Lake Rd. for about 1/2 mile
Turn right onto Dodge Ridge Rd. for about 3/4 mile
Turn right at the Pinecrest Chalet entrance—look for the big bear!
      </pre>

      <div class="margin-bottom-3">
        <div class="section__item__title margin-bottom-1">
          Airports
        </div>
        <div>
          Oakland (144 miles)
        </div>
        <div>
          Sacramento (146 miles)
        </div>
        <div>
          Fresno (148 miles)
        </div>
        <div>
          San Francisco (163 miles)
        </div>
      </div>

      <div class="section__item__title">
        Lodging
      </div>
      <pre>
Pinecrest Chalet (The Venue)
  https://alumni.berkeley.edu/travel/pinecrest-chalet/planning-your-trip/accommodations
McCaffrey House B&B
  https://mccaffreyhouse.com/yosemite-area-bed-and-breakfast-lodging/
Pinecrest Resort
  http://pinecrestlakeresort.com/pinecrest-lodging.html
Strawberry Inn
  http://www.strawberryinn.com/
      </pre>

      <div class="section__item__title">
        Local Activities
      </div>
      <pre>
Hiking
  https://www.alltrails.com/trail/us/california/cleos-bath-trail
  https://www.alltrails.com/trail/us/california/pinecrest-peak-trail
  https://www.alltrails.com/trail/us/california/pinecrest-lake-loop
Paddle Boating
  http://pinecrestlakeresort.com/pinecrest-marina.html
Kayaking
  http://pinecrestlakeresort.com/pinecrest-marina.html
Horse Back Riding:
  http://www.aspenmeadowpackstation.com/
Climbing
  https://www.mountainproject.com/area/107299550/sonora-pass-highway-108
      </pre>
    </div>
  </div>
</div>
</template>

<script>
import hero from '../components/Hero.vue';

export default {
  name: 'Info',
  components: {
    hero,
  },
}
</script>

<style>
</style>
