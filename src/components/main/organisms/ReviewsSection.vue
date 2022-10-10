<template>
  <div class="reviews-section">
    <TitleComponent
      title="People are prasing Maxcoach"
      description="What makes them love us?"
    />
    <div class="review-cards-container">
      <div
        v-for="(review, item) in Reviews"
        :key="item"
        @click="changeVisibility(item)"
      >
        <div
          v-if="
            item >= SelectedButton * REVIEWS_TO_DISPLAY &&
            item < SelectedButton * REVIEWS_TO_DISPLAY + REVIEWS_TO_DISPLAY
          "
        >
          <ReviewCardComponent
            :title="review.title"
            :text="review.text"
            :pic="review.pic"
            :name="review.name"
            :job="review.job"
            :visible="VisibilityIndex == item ? true : false"
          />
        </div>
      </div>
    </div>
    <div class="buttons-container">
      <div v-for="(button, index) in Buttons" :key="index">
        <div
          class="custom-radio"
          @click="changeSelectedButton(index)"
          :class="index == SelectedButton ? 'button-active' : ''"
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
import TitleComponent from "@/components/main/molecules/TitleComponent.vue";
import ReviewCardComponent from "@/components/main/molecules/ReviewCardComponent.vue";
import Reviews from "@/data/reviews.json";

export default {
  name: "ReviewsSection",
  components: {
    TitleComponent,
    ReviewCardComponent,
  },
  data() {
    return {
      Reviews,
      VisibilityIndex: 1,
      Buttons: 0,
      SelectedButton: 0,
      REVIEWS_TO_DISPLAY: 3,
    };
  },
  created() {
    this.getButtons();
  },
  methods: {
    changeVisibility(i) {
      console.log("visibility index is:", i);
      this.VisibilityIndex = i;
    },
    changeSelectedButton(i) {
      this.SelectedButton = i;
      this.VisibilityIndex = this.SelectedButton * this.REVIEWS_TO_DISPLAY + 1;
      console.log("selected button:", this.SelectedButton);
      console.log("visibility index is:", this.VisibilityIndex);
    },
    getButtons() {
      let division = Math.ceil(this.Reviews.length / this.REVIEWS_TO_DISPLAY);
      this.Buttons = division;
      console.log("number of buttons: ", division);
      console.log("number of reviews: ", this.Reviews.length);
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.reviews-section {
  @include AM_small_padding;
  background-color: rgb(248, 248, 248);
  .review-cards-container {
    @include flex-row;
    justify-content: center;
    margin: 4% 0%;
  }
  .buttons-container {
    @include flex-row;
    width: 100%;
    justify-content: center;
    align-items: center;
    .custom-radio {
      height: 8px;
      width: 8px;
      background-color: lightgray;
      border-radius: 50%;
      margin: 3px;
    }
    .custom-radio:hover {
      cursor: pointer;
    }
    .button-active {
      height: 10px;
      width: 10px;
      background-color: black;
    }
  }
}
</style>
