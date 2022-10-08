<template>
  <main>
    <!-- First Section: Jumbotron -->
    <section>
      <JumbotronComponent />
    </section>
    <section>
      <FeaturesComponent />
    </section>
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
