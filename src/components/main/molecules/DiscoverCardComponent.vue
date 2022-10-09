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
@import "@/main.scss";
.discover-card {
  @include flex-col;
  justify-content: space-between;
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
    text-align: center;
    h4 {
      margin-bottom: 10px;
      font-size: 1rem;
    }
    p {
      font-size: 0.8rem;
    }
  }
  .link-area {
    @include flex-col;
    height: 12%;
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
.discover-card:hover {
  .link-area {
    background-color: $jungle_green;
    a {
      color: white;
    }
    a:visited {
      color: white;
    }
  }
}
</style>
