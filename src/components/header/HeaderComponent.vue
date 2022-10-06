<template>
  <header>
    <!-- <script src="https://kit.fontawesome.com/710259c6f3.js" crossorigin="anonymous"></script> -->
    <div class="img-container">
      <img src="@/assets/img/dark-logo.png" alt="max_coach_logo" />
    </div>
    <div class="lists-container">
      <div
        class="list"
        v-for="list in dropdowns"
        :key="list.title"
        @click="setActiveList(list)"
      >
        {{ list.title }} <i class="fa-solid fa-caret-down"></i>
        <div v-if="list === activeIndex">
          <ul>
            <li v-for="link in list.links" :key="link.name">
              <a :href="link.link">{{ link.name }}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div>
      <div
        class="languages list"
        @click="displayedLanguages = !displayedLanguages"
      >
        <img
          :src="require('../../assets/img/' + languages[0].image)"
          alt="language"
          class="language-img"
        />
        {{ languages[0].language }}
        <ul v-if="displayedLanguages">
          <li
            v-for="(language, index) in languages"
            :key="index"
            @click="changeLanguage(index)"
          >
            <p v-if="language.language != languages[0].language">
              <img
                :src="require('../../assets/img/' + language.image)"
                alt="language"
                class="language-img"
              />
              {{ language.language }}
            </p>
          </li>
        </ul>
      </div>
      <div class="user"></div>
      <div class="search-bar"></div>
    </div>
  </header>
</template>

<script>
import dropdowns from "@/data/headerDropdowns.json";
import languages from "@/data/languages.json";

export default {
  name: "HeaderComponent",
  data() {
    return {
      dropdowns,
      languages,
      activeIndex: 0,
      displayedLanguages: true,
    };
  },
  mounted() {
    console.log("dropdown lists in header: ", dropdowns);
    console.log("languages image:", languages[0].image);
  },
  methods: {
    setActiveList(i) {
      if (i == this.activeIndex) {
        return (this.activeIndex = 0);
      }
      this.activeIndex = i;
      return this.activeIndex;
    },
    changeLanguage(i) {
      [this.languages[0], this.languages[i]] = [
        this.languages[i],
        this.languages[0],
      ];
    },
  },
};
</script>

<style lang="scss" scoped>
@import "@/main.scss";
header {
  @include flex-row;
  justify-content: space-between;
  align-items: center;
  padding: 0% 2%;
  font-size: 0.9rem;
  min-height: 7vh;
  max-height: 7vh;
  width: 100%;
  border: solid black 1px;
  .img-container {
    transform: translateX(70%);
    img {
      height: 3vh;
    }
  }
  .lists-container {
    @include flex-row;
    .list {
      @include flex-col;
      position: relative;
      margin: 0px 14px;
    }
  }
  ul {
    position: absolute;
    list-style-type: none;
    padding: 0px 5px;
    background-color: white;
    transform: translate(-5px, 5px);
    border: solid black 1px;
    li {
      margin: 7px 0px;
      min-width: 100px;
      a {
        color: black;
      }
    }
  }
  .language-img {
    height: 2vh;
    margin-right: 5px;
  }
}
</style>
