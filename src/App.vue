<template>
  <div id="app">
    <HeaderComponent/>
    <MainComponent/>
    <FooterComponent/>
  </div>
</template>

<script>
import HeaderComponent from '@/components/header/HeaderComponent.vue';
import MainComponent from '@/components/main/MainComponent.vue';
import FooterComponent from '@/components/footer/FooterComponent.vue';



export default {
  name: 'App',
  components: {
    HeaderComponent,
    MainComponent,
    FooterComponent

  }
}
</script>

<style lang="scss">
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;

}
</style>
