<template>
  <div class="jumbotron">
    <div class="left-side">
      <p>New Challenges New Skills</p>
      <h1>Build your own life coaching business</h1>
      <p>Whole-life business coaching for committed entrepeneurs</p>
      <ButtonComponent
        text="Get started today"
        :full="true"
        link="https://google.com"
      />
    </div>
    <div class="right-side">
      <img src="@/assets/img/home-business-hero-avatar.png" alt="" />
    </div>
    <div class="action-buttons">
      <div>O</div>
      <div>O</div>
      <div>O</div>
      <div>O</div>
    </div>
  </div>
</template>

<script>
import ButtonComponent from "@/components/utils/ButtonComponent.vue";

export default {
  name: "JumbotronComponent",
  components: {
    ButtonComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.jumbotron {
  @include flex-row;
  max-height: 70vh;
  background-color: $link_water_ligth_vibrant;
  position: relative;
  .left-side {
    padding: 10% 0% 10% 10%;
    width: 50%;
    display: flex;
    flex-direction: column;
    gap: 20px;
    justify-content: center;
    img {
      width: 100%;
      object-fit: contain;
    }
  }
  .right-side {
    @include flex-row;
    width: 50vw;
    flex-grow: 1;
    background-image: url("@/assets/img/home-business-hero-global-image.png");
    background-size: contain;
    background-repeat: no-repeat;
  }
  .action-buttons {
    position: absolute;
    display: flex;
    right: 0;
    top: 20%;
    flex-direction: column;
    padding: 5px;
    background-color: white;
    box-shadow: 0px 1px 3px -1px black;
  }
}
</style>
