<template>
  <v-app>
    <div id="app-wrapper">
      <HomeSection />
      <AboutSection />
      <MyServices />
      <ContactSection />
    </div>
  </v-app>
</template>

<script>
import HomeSection from './components/HomeSection.vue';
import AboutSection from './components/AboutSection.vue';
import MyServices from './components/MyServices.vue';
import ContactSection from './components/ContactSection.vue';


export default {
  name: 'App',
  components: {
    HomeSection,
    AboutSection,
    MyServices,
    ContactSection,
  },
};
</script>


<style>

html,
body,
#app {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  height: 100%;
  overflow-x: hidden;
}
</style>
