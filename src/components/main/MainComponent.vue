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

    <!-- Fourth Section: Explore Section-->
    <section>
      <CoursesSection />
    </section>

    <!-- Fifth Section: Q&A Section-->
    <section>
      <QandASection />
    </section>

    <!-- Sixth Section: Events Section-->
    <section>
      <EventsSection />
    </section>

    <!-- Seventh Section: Reviews Section-->
    <section>
      <ReviewsSection />
    </section>

    <!-- Eigth Section: Newsletter Section-->
    <section>
      <NewsletterSection />
    </section>
  </main>
</template>

<script>
import JumbotronSection from "@/components/main/organisms/JumbotronSection.vue";
import FeaturesSection from "@/components/main/organisms/FeaturesSection.vue";
import DiscoverSection from "@/components/main/organisms/DiscoverSection.vue";
import CoursesSection from "@/components/main/organisms/CoursesSection.vue";
import QandASection from "@/components/main/organisms/QandASection.vue";
import EventsSection from "@/components/main/organisms/EventsSection.vue";
import ReviewsSection from "@/components/main/organisms/ReviewsSection.vue";
import NewsletterSection from "@/components/main/organisms/NewsletterSection.vue";

export default {
  name: "MainComponent",
  components: {
    JumbotronSection,
    FeaturesSection,
    DiscoverSection,
    CoursesSection,
    QandASection,
    EventsSection,
    ReviewsSection,
    NewsletterSection,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
</style>
