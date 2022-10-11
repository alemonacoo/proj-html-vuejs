<template>
  <div class="event">
    <div class="left-side">
      <p id="place">{{ place }}</p>
      <h4>{{ name }}</h4>
    </div>
    <div class="right-side">
      <p id="day">{{ day }}</p>
      <p>{{ month }}</p>
      <ButtonComponent
        id="custom-event-button"
        text="Get Ticket"
        :full="true"
        link="https://google.com"
      />
    </div>
  </div>
</template>

<script>
import ButtonComponent from "@/components/atoms/ButtonComponent.vue";

export default {
  name: "EventCardComponent",
  props: {
    name: String,
    day: Number,
    month: String,
    place: String,
  },
  components: {
    ButtonComponent,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.event {
  @include flex-row;
  justify-content: space-between;
  background-color: rgb(248, 248, 248);
  border-radius: 5px;
  padding: 10px;
  margin: 10px;
  width: 400px;
  height: 120px;
  .left-side {
    @include flex-col;
    gap: 10px;
    width: 70%;
    #place {
      font-size: 0.8rem;
      color: grey;
    }
  }
  .right-side {
    @include flex-col;
    justify-content: space-between;
    align-items: center;

    #day {
      font-size: 2.5rem;
      color: $jungle_green;
    }
  }
  #custom-event-button {
    width: 100px;
    padding: 5px;
    border-radius: 5px;
    font-size: 0.7rem;
  }
}
.event:hover {
  background-color: white;
  box-shadow: 1px 1px 5px 4px lightgrey;
  border-left: 4px solid $jungle_green;
}
</style>
