<template>
  <footer>
    <div class="footer-lists-container">
      <div v-for="list in FooterLists" :key="list.title">
        <FooterListCard
          class="footer-list-card"
          :title="list.title"
          :list="list.list"
        />
      </div>
    </div>
    <div class="bottom-footer">
      <div></div>
      <p>&copy; 2020 Maxcoach. All rights Reserved</p>
      <div class="up-button" @click="am_scroll">&uarr;</div>
    </div>
  </footer>
</template>

<script>
import FooterListCard from "@/components/footer/molecules/FooterListCard.vue";
import FooterLists from "@/data/FooterLists.json";

export default {
  name: "FooterComponent",
  components: {
    FooterListCard,
  },
  data() {
    return {
      FooterLists,
    };
  },
  methods: {
    am_scroll() {
      window.scrollTo({ top: 0, behavior: "smooth" });
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
footer {
  min-height: 40vh;
  background-color: rgb(23, 22, 33);
  .footer-lists-container {
    padding: 7% 15%;
    @include flex-row;
    flex-wrap: wrap;
    height: 100%;
    justify-content: space-between;
  }
  .bottom-footer {
    @include flex-row;
    justify-content: space-between;
    height: 8vh;
    color: white;
    align-items: center;
    padding: 10px;
    p {
      font-size: 0.8rem;
      color: grey;
    }
    .up-button {
      height: 5vh;
      width: 5vh;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 50%;
      background-color: $jungle_green;
    }
    .up-button:hover {
      cursor: pointer;
      background-color: rgb(63, 29, 99);
    }
  }
}
</style>
