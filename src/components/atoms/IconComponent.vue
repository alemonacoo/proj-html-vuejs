<template>
  <font-awesome-icon :icon="'fa-' + type + ' ' + 'fa-' + icon" />
</template>

<script>
import Vue from "vue";
import { library } from "@fortawesome/fontawesome-svg-core";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import {
  faMagnifyingGlass,
  faRulerCombined,
  faBook,
  faChevronDown,
  faLifeRing,
  faCartShopping,
} from "@fortawesome/free-solid-svg-icons";
import {
  faCircleDown,
  faCircleUp,
  faCircleUser,
  faNoteSticky,
  faUser,
} from "@fortawesome/free-regular-svg-icons";

library.add(
  faCircleUser,
  faMagnifyingGlass,
  faChevronDown,
  faRulerCombined,
  faLifeRing,
  faBook,
  faCartShopping,
  faNoteSticky,
  faUser,
  faCircleUp,
  faCircleDown
);
Vue.component("font-awesome-icon", FontAwesomeIcon);
Vue.config.productionTip = false;

export default {
  name: "IconComponent",
  props: {
    type: String,
    icon: String,
  },
};
</script>

<style lang="scss" scoped></style>
