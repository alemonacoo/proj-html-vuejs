<template>
  <div class="discover-section">
    <TitleComponent
      title="Let's Dream Big Together"
      description="Explore How can I help you"
    />
    <div class="discover-cards-container">
      <div v-for="card in discoverCards" :key="card.title">
        <DiscoverCardComponent
          :title="card.title"
          :description="card.description"
          :img="card.img"
        />
      </div>
    </div>
  </div>
</template>

<script>
import TitleComponent from "@/components/main/molecules/TitleComponent.vue";
import DiscoverCardComponent from "@/components/main/molecules/DiscoverCardComponent.vue";
import discoverCards from "@/data/discoverCards.json";

export default {
  name: "DiscoverSection",
  components: {
    TitleComponent,
    DiscoverCardComponent,
  },
  data() {
    return {
      discoverCards,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.discover-section {
  @include AM_grey_background;
  @include AM_small_padding;
  .discover-cards-container {
    @include flex-row;
    flex-wrap: wrap;
    justify-content: center;
    margin: 4% 0%;
  }
}
</style>
