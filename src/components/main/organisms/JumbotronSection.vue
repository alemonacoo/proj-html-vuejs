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
      <div>
        <IconComponent class="icon" type="solid" icon="ruler-combined" />
      </div>
      <div>
        <IconComponent class="icon" type="solid" icon="life-ring" />
      </div>
      <div>
        <IconComponent class="icon" type="solid" icon="book" />
      </div>
      <div>
        <IconComponent class="icon" type="solid" icon="cart-shopping" />
      </div>
    </div>
  </div>
</template>

<script>
import ButtonComponent from "@/components/atoms/ButtonComponent.vue";
import IconComponent from "@/components/atoms/IconComponent.vue";

export default {
  name: "JumbotronSection",
  components: {
    ButtonComponent,
    IconComponent,
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
    padding: 10%;
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
    @include flex-col;
    position: absolute;
    right: 0;
    top: 15%;
    padding: 6px;
    background-color: white;
    box-shadow: 0px 1px 3px -1px black;
    gap: 5px;

    .icon {
      font-size: 0.7rem;
    }
    .icon:hover {
      cursor: pointer;
      color: grey;
    }
  }
}
</style>
