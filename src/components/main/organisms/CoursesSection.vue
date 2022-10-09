<template>
  <div class="courses-section">
    <TitleComponent
      title="Let's Dream Big Together"
      description="Explore How can I help you"
    />
    <div class="courses-cards-container">
      <div v-for="course in Courses" :key="course.title">
        <CourseCardComponent
          :title="course.title"
          :price="course.price"
          :description="course.description"
          :hours="course.hours"
          :students="course.students"
          :img="course.img"
        />
      </div>
    </div>
  </div>
</template>

<script>
import TitleComponent from "@/components/main/molecules/TitleComponent.vue";
import CourseCardComponent from "@/components/main/molecules/CourseCardComponent.vue";
import Courses from "@/data/coursesCards.json";

export default {
  name: "CoursesSection",
  components: {
    TitleComponent,
    CourseCardComponent,
  },
  data() {
    return {
      Courses,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.courses-section {
  @include AM_small_padding;
  .courses-cards-container {
    @include flex-row;
    flex-wrap: wrap;
    justify-content: center;
    margin: 4% 0%;
  }
}
</style>
