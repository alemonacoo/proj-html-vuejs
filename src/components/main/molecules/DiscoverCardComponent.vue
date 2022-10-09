<template>
  <div class="discover-card">
    <img :src="require('@/assets/img/' + img)" alt="" />
    <div class="text-area">
      <h4>{{ title }}</h4>
      <p>{{ description }}</p>
    </div>
    <div class="link-area">
      <strong> <a href="https://google.com">Discover Now &#8594;</a></strong>
    </div>
  </div>
</template>

<script>
export default {
  name: "DiscoverCardComponent",
  props: {
    img: String,
    title: String,
    description: String,
  },
};
</script>

<style lang="scss" scoped>
.discover-card {
  @import "@/main.scss";
  margin: 10px;
  height: 52vh;
  width: 250px;
  box-shadow: 1px 1px 5px 4px lightgrey;
  border-radius: 5px;
  overflow: hidden;

  img {
    object-fit: cover;
    width: 100%;
    height: 50%;
  }
  .text-area {
    @include flex-col;
    text-align: center;
    gap: 10px;
    height: 30%;
    justify-content: center;
    align-items: center;
    h4 {
      font-size: 1rem;
    }
    p {
      font-size: 0.8rem;
    }
  }
  .link-area {
    @include flex-col;
    height: 20%;
    justify-content: center;
    align-items: center;
    border-top: solid 0.5px lightgrey;

    a {
      font-size: 0.8rem;
      color: $jungle_green;
      text-decoration: none;
    }
    a:visited {
      color: $jungle_green;
    }
  }
}
</style>
