<template>
  <div class="hello">
    <div class="teaser-container">
      <div class="teaser">
        <div class="teaser__title">
          {{ msg }}
        </div>
        <div class="teaser__blurb">
          More to come
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Sean & Alice'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello {
  height: 100vh;
  background: url('./../assets/F01A1952.jpg') no-repeat center center fixed;
  background-size: cover;
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
    font-size: 56px;
    font-weight: 600;
  }

  .teaser__blurb {
    font-size: 24px;
    font-weight: 400;
    opacity: 0.6;
  }

</style>
