<template>
  <div class="QandA-section">
    <img
      id="wallpaper-world"
      src="@/assets/img/background-map-dots-top-right-transparent.png"
      alt="wallpaperNotFound"
    />
    <img
      id="wallpaper-square"
      src="@/assets/img/maxcoach-shape-07.png"
      alt="wallpaperNotFound"
    />
    <div class="left-side">
      <img src="@/assets/img/home-business-video-poster-670x450.jpg" alt="" />
      <img id="youtube" src="@/assets/img/icon-youtube-play.png" alt="" />
    </div>
    <div class="right-side">
      <h2>To Thrive In Business Today, You'll Need A Good Plan</h2>
      <div>
        <div
          v-for="(QandA, index) in QandAs"
          :key="index"
          @click="ActivateQandA(index)"
        >
          <QandACard
            :question="QandA.question"
            :answer="QandA.answer"
            :status="ActiveIndex == index ? true : false"
          />
          <hr />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import QandAs from "@/data/QandA.json";
import QandACard from "@/components/main/molecules/QandACard.vue";

export default {
  name: "QandASection",
  components: {
    QandACard,
  },
  data() {
    return { QandAs, ActiveIndex: -1 };
  },
  methods: {
    ActivateQandA(i) {
      if (i === this.ActiveIndex) {
        return (this.ActiveIndex = -1);
      }
      console.log(i);
      return (this.ActiveIndex = i);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.QandA-section {
  @include flex-row;
  position: relative;
  justify-content: center;
  padding: 5% 10%;
  height: 80vh;
  background-color: $tuna;
  #wallpaper-world {
    position: absolute;
    width: 56%;
    top: 0;
    right: 0;
  }
  #wallpaper-square {
    position: absolute;
    width: 113px;
    bottom: 10px;
    left: 30px;
  }
  .left-side {
    @include flex-row;
    height: 100%;
    width: 45%;
    position: relative;
    img {
      width: 100%;
      object-fit: contain;
      border-radius: 5px;
    }
    #youtube {
      position: absolute;
      height: 50px;
      top: calc(50% - 25px);
    }
  }
  .right-side {
    position: relative;
    z-index: 1;
    padding: 30px;
    width: 50%;
    @include flex-col;
    justify-content: space-evenly;
    color: white;
    hr {
      border-top: none;
      border: solid 1px rgba(255, 255, 255, 0.5);
    }
  }
}
</style>
