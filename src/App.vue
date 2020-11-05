<template>
  <div class="app">
    <!-- <AboutMe></AboutMe> -->
    <component v-bind:is="componentsTab[whichComponent]"></component>
    <Navigation :to-down="nameToDown" :to-up="nameToUp"></Navigation>
  </div>
</template>

<script>
import AboutMe from "./components/AboutMe.vue";
import Skills from "./components/Skills.vue";
import MyProfile from "./components/MyProfile.vue";
import Projects from "./components/Projects.vue";
import Navigation from "./components/Navigation.vue";
export default {
  components: {
    AboutMe,
    Skills,
    Navigation,
    Projects,
    MyProfile,
  },
  computed: {
    nameToUp() {
      if (this.whichComponent >= this.componentsTab.length - 1) {
        return this.componentsTab[0];
      } else {
        return this.componentsTab[this.whichComponent + 1];
      }
    },
    nameToDown() {
      if (this.whichComponent - 1 < 0) {
        return this.componentsTab[this.componentsTab.length - 1];
      } else {
        return this.componentsTab[this.whichComponent - 1];
      }
    },
  },
  provide() {
    return { changeTabs: this.changeTabs };
  },
  data() {
    return {
      componentsTab: ["AboutMe", "Projects", "MyProfile", "Skills"],
      whichComponent: 0,
    };
  },
  methods: {
    changeTabs(direction) {
      if (direction === "up") {
        if (this.whichComponent >= this.componentsTab.length - 1) {
          this.whichComponent = 0;
        } else {
          this.whichComponent++;
        }
      } else {
        if (this.whichComponent - 1 < 0) {
          this.whichComponent = this.componentsTab.length - 1;
        } else {
          this.whichComponent--;
        }
      }
    },
  },
};
</script>

<style lang="sass">
@import url('https://fonts.googleapis.com/css2?family=Karla&display=swap')
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital@1&display=swap')
body
  margin: 0
.app
    background: linear-gradient(-45deg, #264653, #2A9D8F,#E9C46A,#F4A261)
    background-size: 400% 400%
    min-height:  100vh
    margin: 0
    padding: 30px 0 30px 0
    animation: gradient 10s ease infinite
@keyframes gradient
    0%
        background-position: 0% 50%
    50%
        background-position: 100% 50%
    100%
        background-position: 0% 50%
::-webkit-scrollbar
  width: 20px


/* Track */
::-webkit-scrollbar-track
  box-shadow: inset 0 0 5px #2a9d8f
  background: #2a9d8f


/* Handle */
::-webkit-scrollbar-thumb
  background: #264653
  border-radius: 10px
</style>
