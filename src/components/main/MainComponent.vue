<template>
  <main>
    <!-- First Section: Jumbotron -->
    <section>
      <JumbotronComponent />
    </section>
  </main>
</template>

<script>
import JumbotronComponent from "@/components/main/JumbotronComponent.vue";

export default {
  name: "MainComponent",
  components: {
    JumbotronComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
</style>
