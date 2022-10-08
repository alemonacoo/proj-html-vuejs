<template>
  <main>
    <!-- First Section: Jumbotron -->
    <section>
      <JumbotronComponent />
    </section>

    <!-- Second Section: Features -->
    <section>
      <FeaturesComponent />
    </section>

    <!-- Third Section: -->
    <section></section>
  </main>
</template>

<script>
import JumbotronComponent from "@/components/main/organisms/JumbotronComponent.vue";
import FeaturesComponent from "@/components/main/organisms/FeaturesComponent.vue";

export default {
  name: "MainComponent",
  components: {
    JumbotronComponent,
    FeaturesComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
</style>
