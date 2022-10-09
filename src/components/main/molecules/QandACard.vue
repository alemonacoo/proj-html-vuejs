<template>
  <div class="QandA">
    <div class="icon-container" :class="status ? 'active' : ''">
      <p v-if="status">A</p>
      <p v-else>C</p>
    </div>
    <div class="text-container" :class="status ? 'active' : ''">
      <h4>
        {{ question }}
      </h4>
      <div class="answer-section" v-if="status">
        <p>{{ answer }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "QandACard",
  props: {
    question: String,
    answer: String,
    status: Boolean,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
.QandA {
  @include flex-row;
  gap: 10px;
  padding: 20px 0px;
  .text-container {
    @include flex-col;
    gap: 8px;
    p {
      font-size: 0.8rem;
    }
  }
}
.active {
  color: $jungle_green;
}
.answer-section {
  color: white;
}
.QandA:hover {
  cursor: pointer;
  .text-container {
    h4 {
      text-decoration: underline;
    }
  }
}
</style>
