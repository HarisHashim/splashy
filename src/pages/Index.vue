<template>
  <q-page class="flex flex-center">
    <div
      class
      style="width:100%;"
    >
      <q-carousel
        v-model="slideName"
        :height="windowHeight"
        class
        arrows
        navigation
        autoplay
      >
        <q-carousel-slide
          :name="1"
          img-src="statics/photo/analog.jpg"
        />
        <q-carousel-slide
          :name="2"
          img-src="statics/photo/bright.jpg"
        />
        <q-carousel-slide
          :name="3"
          img-src="statics/photo/application.jpg"
        />
        <q-carousel-slide
          :name="4"
          img-src="statics/photo/board.jpg"
        />
      </q-carousel>

      <q-card
        :class="{'card-top-right':isOne, 'card-top-left':isTwo,'card-bottom-left':isThree,
        'card-bottom-right':isFour, 'bg-secondary':true}"
        dark
        bordered
        style="width: 100%; max-width: 200px; opacity:0.7;"
      >
        <q-card-section class="text-h6 item-center">
          <div style="color:white; text-align: center;">{{slideText[slideName-1]}}</div>
        </q-card-section>
      </q-card>

      <q-img
        v-if="isFour"
        class="fixed-center q-mt-lg"
        style="width: 310px; height: 91px; opacity:.95; background:white"
        src="statics/photo/snlogo_trans.png"
        spinner-color="white"
      />
    </div>
  </q-page>
</template>

<style>
.my-card {
  width: "100%";
  max-width: "250px;";
}

.card-top-right {
  position: absolute;
  margin-top: 64px;
  margin-right: 64px;
  padding: 16px;
  right: 0;
  top: 0;
}

.card-top-left {
  position: absolute;
  margin-top: 64px;
  margin-left: 64px;
  padding: 16px;
  top: 0;
  left: 0;
}

.card-bottom-left {
  position: absolute;
  margin-bottom: 64px;
  margin-left: 64px;
  padding: 16px;
  bottom: 0;
  left: 0;
}
.card-bottom-right {
  position: absolute;
  margin-bottom: 64px;
  margin-right: 64px;
  padding: 16px;
  bottom: 0;
  right: 0;
}
</style>

<script>
export default {
  name: "PageIndex",
  data() {
    return {
      slideName: 1,
      slideText: [
        "One is the loneliest number ...",
        "Bright idea worthy of bright compensation.",
        "Excellence through design.",
        "Stay tuned, we are coming!"
      ]
    };
  },
  created() {
    this.windowHeight = window.innerHeight + "px";
  },
  computed: {
    isOne() {
      return this.slideName === 1;
    },
    isTwo() {
      return this.slideName === 2;
    },
    isThree() {
      return this.slideName === 3;
    },
    isFour() {
      return this.slideName === 4;
    }
  }
};
</script>
