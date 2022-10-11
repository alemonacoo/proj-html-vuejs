<template>
  <button :class="full ? 'full' : 'empty'">
    <strong>
      <a :href="link">{{ text }}</a></strong
    >
  </button>
</template>

<script>
export default {
  name: "ButtonComponent",
  props: {
    text: String,
    full: Boolean,
    link: String,
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
button {
  width: fit-content;
  padding: 8px 30px;
  border-radius: 5px;
}
.full {
  color: white;
  background-color: $jungle_green;
  border: solid 1px $jungle_green;
  a:visited {
    color: white;
  }
}
.empty {
  color: $jungle_green;
  background-color: white;
  border: solid 1px lightgray;
  a:visited {
    color: $jungle_green;
  }
}
a {
  text-decoration: none;
}
button:hover {
  background-color: rgb(63, 29, 99);
  border: solid 1px rgb(63, 29, 99);
  cursor: pointer;
  color: white;
  border: none;
  a:visited {
    color: white;
  }
}
</style>
