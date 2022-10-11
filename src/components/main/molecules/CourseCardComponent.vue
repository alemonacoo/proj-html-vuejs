<template>
  <div class="course-card">
    <img :src="require('@/assets/img/' + img)" alt="" />
    <div class="description">
      <p id="price">
        <strong>${{ price }}.00</strong>
      </p>
      <h4>{{ title }}</h4>
      <div class="description-more">
        <p>
          <span>
            <IconComponent type="regular" icon="note-sticky" />
            {{ hours }} Lessons</span
          ><span>
            <IconComponent type="regular" icon="user" />
            {{ students }} Students</span
          >
        </p>
        <p>{{ description }}</p>
      </div>
    </div>
  </div>
</template>

<script>
import IconComponent from "@/components/atoms/IconComponent.vue";

export default {
  name: "CourseCardComponent",
  props: {
    title: String,
    price: Number,
    description: String,
    hours: Number,
    students: Number,
    img: String,
  },
  components: {
    IconComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.course-card {
  @include flex-col;
  justify-content: flex-end;
  position: relative;
  margin: 10px;
  height: 52vh;
  width: 240px;
  z-index: 1;
  overflow: hidden;
  border-radius: 5px;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    position: absolute;
  }
  .description {
    @include flex-col;
    gap: 5px;
    color: white;
    margin: 4%;
    position: relative;
    z-index: 1;
    box-shadow: 1px 1px 39px 42px rgb(0 0 0 / 70%);
    background-color: rgba(0, 0, 0, 0.7);
    #price {
      color: $jungle_green;
      font-weight: 800;
    }
    h4 {
      font-size: 1rem;
    }
    p {
      font-size: 0.8rem;
      span {
        margin-right: 5px;
      }
    }
    .description-more {
      display: none;
      font-size: 0.8rem;
    }
  }
}
.course-card:hover {
  .description-more {
    @include flex-col;
    gap: 5px;
    z-index: 1;
  }
}
</style>
