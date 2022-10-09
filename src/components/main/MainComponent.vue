<template>
  <main>
    <!-- First Section: Jumbotron -->
    <section>
      <JumbotronSection />
    </section>

    <!-- Second Section: Features -->
    <section>
      <FeaturesSection />
    </section>

    <!-- Third Section: Discover Section-->
    <section>
      <DiscoverSection />
    </section>
  </main>
</template>

<script>
import JumbotronSection from "@/components/main/organisms/JumbotronSection.vue";
import FeaturesSection from "@/components/main/organisms/FeaturesSection.vue";
import DiscoverSection from "@/components/main/organisms/DiscoverSection.vue";

export default {
  name: "MainComponent",
  components: {
    JumbotronSection,
    FeaturesSection,
    DiscoverSection,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
</style>
