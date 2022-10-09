<template>
  <div class="title">
    <p>{{ title }}</p>
    <h2>{{ description }}</h2>
  </div>
</template>

<script>
export default {
  name: "TitleComponent",
  props: {
    title: String,
    description: String,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.title {
  @include flex-col;
  text-align: center;
  gap: 15px;
  p {
    color: $jungle_green;
    font-size: 1rem;
  }
  h2 {
    font-size: 1.5rem;
  }
}
</style>
