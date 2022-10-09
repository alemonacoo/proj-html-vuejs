<template>
  <div class="feature-card">
    <div class="img-container">
      <img :src="require('@/assets/img/' + img)" alt="feature_card_img" />
    </div>
    <div class="description">
      <h3>{{ title }}</h3>
      <p>{{ description }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "FeatureCardComponent",
  props: {
    title: String,
    description: String,
    img: String,
  },
};
</script>

<style lang="scss" scoped>
.feature-card {
  @import "@/main.scss";
  @include flex-row;
  margin: 15px 0px;
  width: 250px;
  .img-container {
    width: 20%;
    img {
      width: 100%;
    }
  }
  .description {
    @include flex-col;
    gap: 10px;
    width: 80%;
    h3 {
      font-size: 1rem;
    }
    p {
      font-size: 0.8rem;
    }
  }
}
</style>
