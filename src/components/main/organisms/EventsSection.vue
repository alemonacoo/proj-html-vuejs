<template>
  <div class="grey-curved-wallpaper-container">
    <div class="events-section">
      <TitleComponent
        title="Wanna transform your life?"
        description="Upcoming Events"
      />
      <div class="event-cards-container">
        <div v-for="event in Events" :key="event.name">
          <EventCardComponent
            :name="event.name"
            :day="event.day"
            :month="event.month"
            :place="event.place"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import TitleComponent from "@/components/main/molecules/TitleComponent.vue";
import EventCardComponent from "@/components/main/molecules/EventCardComponent.vue";
import Events from "@/data/events.json";

export default {
  name: "EventsSection",
  components: {
    TitleComponent,
    EventCardComponent,
  },
  data() {
    return {
      Events,
    };
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.grey-curved-wallpaper-container {
  background-color: rgb(248, 248, 248);
}
.events-section {
  background-color: white;
  border-bottom-right-radius: 70% 20%;
  @include AM_big_padding;
  @include flex-col;
  .event-cards-container {
    @include flex-row;
    flex-wrap: wrap;
    margin: 4% 0%;
    justify-content: space-evenly;
  }
}
</style>
