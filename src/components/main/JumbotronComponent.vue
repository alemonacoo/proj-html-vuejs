<template>
  <div class="jumbotron">
    <div class="left-side">
      <ButtonComponent text="prova" :full="true" link="https://google.com" />
      <ButtonComponent text="prova" :full="false" link="https://google.com" />
    </div>
    <div class="righ-side">prova</div>
    <div class="action-buttons"></div>
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
  min-height: 70vh;
  background-color: $link_water_ligth_vibrant;
  background-image: "@/assets/img/home-business-hero-global-image.png";
  padding: 0% 10%;
  position: relative;
  .left-side {
    height: 100%;
    width: 50%;
  }
  .right-side {
    height: 100%;
    width: 50%;
  }
  .action-buttons {
    position: absolute;
  }
}
</style>
