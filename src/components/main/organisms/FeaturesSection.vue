<template>
  <div class="features-component">
    <TitleComponent
      title="Let's Dream Big Together"
      description="We are pioneers of the digital approach, using leading-edge technology
        to simplify procedures and apply executive coaching in the new age of
        digitalization"
    />
    <div class="feature-cards-container">
      <FeatureCardComponent
        title="One to one"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_01.png"
      />
      <FeatureCardComponent
        title="Anywhere"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_02.png"
      />
      <FeatureCardComponent
        title="On Time"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_03.png"
      />
      <FeatureCardComponent
        title="Online Courses"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_04.png"
      />
      <FeatureCardComponent
        title="Consulting"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_05.png"
      />
      <FeatureCardComponent
        title="Self Development"
        description="Lorem ipsum dolor sit amet consectetur adipisicing elit. Recusandae, nulla error!"
        img="feature_img_06.png"
      />
    </div>
    <div class="buttons-container">
      <ButtonComponent
        text="Learn more"
        :full="false"
        link="https://google.com"
      />
      <ButtonComponent
        text="Get started today"
        :full="true"
        link="https://google.com"
      />
    </div>
  </div>
</template>

<script>
import ButtonComponent from "@/components/atoms/ButtonComponent.vue";
import FeatureCardComponent from "@/components/main/molecules/FeatureCardComponent.vue";
import TitleComponent from "@/components/main/molecules/TitleComponent.vue";

export default {
  name: "FeaturesSection",
  components: {
    ButtonComponent,
    FeatureCardComponent,
    TitleComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.features-component {
  @include flex-col;
  @include AM_big_padding;
  align-items: center;
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
  .feature-cards-container {
    @include flex-row;
    margin: 5% 0%;
    flex-wrap: wrap;
    width: 100%;
    justify-content: space-evenly;
    align-items: center;
  }
  .buttons-container {
    @include flex-row;
    gap: 10px;
  }
}
</style>
