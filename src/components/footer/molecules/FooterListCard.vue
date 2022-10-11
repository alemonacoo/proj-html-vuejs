<template>
  <div class="list">
    <div id="filler-title" v-if="title === ''">
      <h3>Filler</h3>
    </div>
    <div v-else>
      <h3>{{ title }}</h3>
    </div>
    <ul>
      <li v-for="item in list" :key="item.name">
        <a :href="item.link">{{ item.name }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "FooterListCard",
  props: {
    title: String,
    list: Array,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.list {
  @include flex-col;
  margin: 10px;
  #filler-title {
    opacity: 0;
  }
  h3 {
    font-size: 1rem;
    margin-bottom: 5px;
    color: white;
  }
  ul {
    @include flex-col;
    gap: 5px;
    list-style-type: none;
    font-size: 0.8rem;
    color: grey;
    a {
      color: grey;
      text-decoration: none;
    }
    a:visited {
      color: grey;
    }
    a:hover {
      text-decoration: underline;
    }
  }
}
</style>
