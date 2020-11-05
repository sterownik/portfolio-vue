<template>
  <div>
    <h2>My Projects</h2>
    <div class="col-lg-9   col-11 box mx-auto">
      <div
        :style="{
          backgroundImage:
            'url(' + require('@/assets/projects/' + project.src + '.png') + ')',
        }"
        class="project-style "
        :key="project.id"
        v-for="project in projects"
      >
        <h1>{{ project.name }}</h1>
        <h5 class="languages">{{ project.languages }}</h5>
        <div @click="goToSite(project.linkGit)" class="github">
          <img src="../assets/projects/github.png" alt="" />
        </div>
        <div @click="goToSite(project.toSee)" class="look">
          <img src="../assets/projects/look.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  methods: {
    goToSite(item) {
      window.location.href = item;
    },
  },
  data() {
    return {
      projects: [
        {
          id: 1,
          src: "Fiszki",
          name: "Fiszki",
          languages: "#android_app",
          linkGit: "https://github.com/sterownik/mFiszki",
          toSee:
            "https://play.google.com/store/apps/details?id=appmfiszki.mfiszkiapp.mfiszki",
        },
        {
          id: 2,
          src: "Referee",
          name: "Referee Master",
          languages: "#android_app",
          linkGit: "https://github.com/sterownik/Referee-Master",
          toSee:
            "https://play.google.com/store/apps/details?id=refereemaster.refereemaster.refereemaster",
        },
        {
          id: 3,
          src: "coronovirus",
          name: "mVirus",
          languages: "#web_app",
          linkGit: "https://github.com/sterownik/mCoronovirus",
          toSee: "https://sterownik.github.io/mCoronovirus/",
        },
        {
          id: 4,
          src: "exchange",
          name: "Exchange Money",
          languages: "#web_app",
          linkGit: "https://github.com/sterownik/Exchange-Money",
          toSee: "https://github.com/sterownik/Exchange-Money",
        },
        {
          id: 5,
          src: "company",
          name: "Example Company",
          languages: "#web_app",
          linkGit: "https://github.com/sterownik/Example-Company",
          toSee: "https://github.com/sterownik/Exchange-Money",
        },
        {
          id: 6,
          src: "random",
          name: "Random Generator",
          languages: "#web_app",
          linkGit: "https://github.com/sterownik/Random-Generator",
          toSee: "https://sterownik.github.io/Random-Generator/",
        },
        {
          id: 7,
          src: "calculator",
          name: "Calculator",
          languages: "#react_app",
          linkGit: "https://github.com/sterownik/Kalkulator-React",
          toSee: "https://sterownik.github.io/Kalkulator-React/",
        },
        {
          id: 8,
          src: "weatherapp",
          name: "Weather App",
          languages: "#vue_app",
          linkGit: "https://github.com/sterownik/weather-app-vue",
          toSee: "https://sterownik.github.io/weather-app-vue/",
        },
      ],
    };
  },
};
</script>
<style lang="sass" scoped>


h2
    text-align: center
    padding: 3vh 0
    font-size: 50px
    font-weight: bold
    font-family: 'Montserrat', sans-serif
    text-shadow: 2px 2px 4px #000000

div div.box
    display: flex
    justify-content: space-around
    padding-bottom: 5vh
    flex-wrap: wrap
    .project-style
        flex-basis: 30%
        height: 300px
        margin-top: 16vh
        background-position: center
        background-repeat: no-repeat
        background-size: cover
        position: relative
        border-radius: 30px
        box-shadow:         3px 3px 5px 6px black
        z-index: 2
        cursor: pointer


        .languages
          position: absolute
          left: 8%
          bottom: 5%
          color: white
        img
          width: 70%
          position: relative
          top: 50%
          left: 50%
          transform: translate(-50%,-50%)
          transition: 0.4s
          &:hover
            transform: translate(-50%,-50%) scale(1.2)


        .github
          top: 0
          position: absolute
          width: 50%
          height: 100%
          left: 0
          &:hover
            &::after
              opacity: 0
          &::after
            height: 100%
            content: ""
            z-index: -1
            transition: 0.5s
            width: 100%
            background-color: #003049
            border-top-left-radius: 30px
            border-bottom-left-radius: 30px
            opacity: 0.5
            top: 0
            left: 0
            position: absolute

        .look
          top: 0
          position: absolute
          height: 100%
          left: 50%

          width: 50%
          &:hover
            &::after
              opacity: 0
          &::after
            height: 100%
            content: ""
            transition: 0.5s
            z-index: -1
            width: 100%
            background-color: #ddd
            border-top-right-radius: 30px
            border-bottom-right-radius: 30px
            opacity: 0.5
            top: 0
            left: 0
            position: absolute
        h1
          position: relative
          top: -6vh
          color: black
          transition: 0.5s
          left: 50%
          text-align: center
          font-family: 'Montserrat', sans-serif
          text-shadow: 2px 2px 4px #ddd
          transform: translate(-50%,-50%)




@media (max-width: 767px)
  div div.box
    .project-style
        margin-top: 12vh
        height: 220px
        flex-basis: 45%
        h1
          font-size: 18px
          top: -4vh
        .languages
          font-size: 12px
</style>
