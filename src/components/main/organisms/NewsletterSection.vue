<template>
  <div class="newsletter-section">
    <img id="circle" src="@/assets/img/maxcoach-shape-01.png" alt="circle" />
    <img
      id="semi-circle"
      src="@/assets/img/maxcoach-shape-02.png"
      alt="circle"
    />
    <img id="square" src="@/assets/img/maxcoach-shape-09.png" alt="circle" />

    <div class="title-container">
      <h1>Subscribe <span>Newsletter</span></h1>
      <p>
        Enter your email address to register to our newsletter subscription
        delivered on a regular basis!
      </p>
    </div>
    <div class="inputs-container">
      <input type="email" name="" id="" placeholder="Enter your email" />
      <ButtonComponent id="custom-email-button" text="subscribe" :full="true" />
    </div>
  </div>
</template>

<script>
import ButtonComponent from "@/components/atoms/ButtonComponent.vue";

export default {
  name: "NewsletterSection",
  components: {
    ButtonComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.newsletter-section {
  @include AM_small_padding;
  @include flex-col;
  height: 40vh;
  position: relative;
  margin-bottom: 5%;
  .title-container {
    @include flex-col;
    gap: 20px;
    position: relative;
    z-index: 2;
    margin-bottom: 30px;
    text-align: center;
    align-items: center;
    h1 {
      font-size: 2rem;
      span {
        font-weight: 100;
        color: $jungle_green;
      }
    }
    p {
      width: 60%;
      color: grey;
    }
  }
  .inputs-container {
    @include flex-row;
    justify-content: center;
    width: 60%;
    align-self: center;
    input {
      border: none;
      border-top-left-radius: 5px;
      border-bottom-left-radius: 5px;
      background-color: rgb(248, 248, 248);
      width: 70%;
      height: auto;
      outline: none;
      padding: 10px;
    }
    #custom-email-button {
      border-top-left-radius: 0;
      border-bottom-left-radius: 0;
    }
  }
  // Wallpaper images
  #circle {
    height: 50px;
    width: 50px;
    position: absolute;
    z-index: 0;
    left: 10%;
    top: 50%;
  }
  #semi-circle {
    height: 50px;
    width: 50px;
    position: absolute;
    z-index: 0;
    right: 10%;
    top: 50%;
  }
  #square {
    height: 110px;
    width: 110px;
    position: absolute;
    z-index: 1;
    right: 9%;
    top: 23%;
  }
}
</style>
