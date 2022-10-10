<template>
  <div class="review" :class="visible ? '' : 'invisible'">
    <div class="actual-review">
      <h4>
        {{ title }}
      </h4>
      <p>
        {{ text }}
      </p>
    </div>
    <div class="author-container">
      <img :src="require('@/assets/img/' + pic)" alt="" srcset="" />
      <div class="author">
        <h5>
          {{ name }}
        </h5>
        <p>/ {{ job }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ReviewCardComponent",
  props: {
    name: String,
    job: String,
    pic: String,
    title: String,
    text: String,
    visible: Boolean,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.review {
  @include flex-col;
  margin: 10px;
  padding: 20px;
  width: 350px;
  height: 260px;
  background-color: white;
  .actual-review {
    @include flex-col;
    gap: 10px;
    height: 80%;
    h4 {
      font-size: 1rem;
    }
  }
  .author-container {
    @include flex-row;
    align-items: center;
    height: 20%;
    img {
      height: 100%;
      border-radius: 50%;
      margin-right: 10px;
    }
    .author {
      @include flex-col;
      gap: 6px;
    }
  }
  p {
    font-size: 0.8rem;
    color: grey;
  }
}
.invisible {
  opacity: 0.3;
}
</style>
