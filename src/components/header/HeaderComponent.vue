<template>
  <header>
    <!-- Left Section: Logo container -->
    <div class="img-container">
      <img src="@/assets/img/dark-logo.png" alt="max_coach_logo" />
    </div>

    <!-- Middle Section: Dropdown Lists -->
    <div class="lists-container">
      <div
        class="list"
        v-for="list in dropdowns"
        :key="list.title"
        @click="setActiveList(list)"
      >
        <p>
          <span>{{ list.title }}</span
          ><span>
            <IconComponent class="icon" type="solid" icon="chevron-down"
          /></span>
        </p>
        <div v-if="list === activeIndex">
          <ul>
            <li v-for="link in list.links" :key="link.name">
              <a :href="link.link">{{ link.name }}</a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Right Section: Languages List, User Infos, Searchbar -->
    <div class="right-side">
      <!-- Languages selector -->
      <!-- Explanation: selected language as first element of array and other languages in ul,
      if another language is selected then languages[0] changes  -->
      <div @click="displayedLanguages = !displayedLanguages">
        <div class="list">
          <div id="selected-language-title">
            <img
              :src="require('../../assets/img/' + languages[0].image)"
              alt="language"
              class="language-img"
            />
            <p id="selected-language">
              {{ languages[0].language }}
              <IconComponent class="icon" type="solid" icon="chevron-down" />
            </p>
          </div>
        </div>
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

      <!-- User -->
      <div class="user">
        <IconComponent class="icon" type="regular" icon="circle-user" />
      </div>

      <!-- Search Bar -->
      <div class="search-bar">
        <input type="text" name="search" placeholder="Search..." />
        <IconComponent class="icon" type="solid" icon="magnifying-glass" />
      </div>
    </div>
  </header>
</template>

<script>
import dropdowns from "@/data/headerDropdowns.json";
import languages from "@/data/languages.json";
import IconComponent from "@/components/atoms/IconComponent.vue";

export default {
  name: "HeaderComponent",
  data() {
    return {
      dropdowns,
      languages,
      activeIndex: 0,
      displayedLanguages: false,
    };
  },
  components: {
    IconComponent,
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
  padding-left: 10%;
  font-size: 0.7rem;
  min-height: 7vh;
  max-height: 7vh;
  width: 100%;
  .img-container {
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
      height: 7vh;
      justify-content: center;
      .icon {
        font-size: 0.5rem;
        margin-left: 4px;
      }
    }
  }
  ul {
    position: absolute;
    list-style-type: none;
    padding: 0px 5px;
    background-color: white;
    transform: translate(0px, 10px);
    box-shadow: 1px 1px 5px 4px lightgrey;
    z-index: 1;
    li {
      margin: 7px 0px;
      min-width: 100px;
      a {
        color: black;
        text-decoration: none;
      }
    }
  }
  .language-img {
    height: 2vh;
    margin-right: 5px;
  }
  .right-side {
    display: flex;
    align-items: center;
    .icon {
      margin: 0px 10px;
      &:hover {
        cursor: pointer;
      }
    }
  }
  #selected-language-title {
    @include flex-row;
    .icon {
      margin-left: 4px;
      font-size: 0.5rem;
    }
  }
  input {
    height: 7vh;
    border: none;
    border-left: solid 1px lightgrey;
    padding: 10px;
    outline: none;
  }
  .list:hover,
  li:hover,
  a:hover {
    cursor: pointer;
    color: lightgray;
  }
}
</style>
