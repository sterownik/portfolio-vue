<template>
  <div class="col-lg-8   col-11 mx-auto">
    <header>Skills</header>
    <div class="content ">
      <VueSlickCarousel v-bind="settings">
        <div class="one-element" :key="skill.id" v-for="skill in skills">
          <h2>{{ skill.title }}</h2>
          <img alt="" :src="require('@/assets/skills/' + skill.src + '.png')" />
          <div class="for-desc">
            <h4>{{ skill.desc }}</h4>
          </div>
        </div>
      </VueSlickCarousel>
    </div>
  </div>
</template>
<script>
import VueSlickCarousel from "vue-slick-carousel";
import "vue-slick-carousel/dist/vue-slick-carousel.css";
// optional style for arrows & dots
import "vue-slick-carousel/dist/vue-slick-carousel-theme.css";
export default {
  components: {
    VueSlickCarousel,
  },
  data() {
    return {
      skills: [
        {
          id: 1,
          title: "HTML5",
          desc:
            "I have knowledge about HTML5, my learning about this languages was start in high school .",
          src: "html",
        },
        {
          id: 2,
          title: "CSS3/SASS",
          desc:
            "I started learning the cascading style sheet in highschool and for 9 months in parallel with HTML I learn more information.",
          src: "sass",
        },
        {
          id: 3,
          title: "JavaScript",
          desc:
            "I also started learning JavaScript in college and after learning HTML and CSS I gain more advanced knowledge.",
          src: "js",
        },
        {
          id: 4,
          title: "Vue.js",
          desc:
            "I still learning about Vue.js, i do some apps in this languages like weather app or another small apps",
          src: "vue5",
        },
        {
          id: 5,
          title: "React.js",
          desc:
            "I learning about  React from internet courses, I did some apps with this library like a calculator in diffrent number system",
          src: "react",
        },
        {
          id: 6,
          title: "Bootstrap 4",
          desc: "I use Bootstrap for responsive in my web apps.",
          src: "bootstrap",
        },
        {
          id: 7,
          title: "Firebase",
          desc:
            "I used Firebase from Google in my Engineering work and in my smaller aps, and I think this is so powerful programming tool",
          src: "firebase3",
        },
        {
          id: 8,
          title: "Java",
          desc:
            "Java is the best known by me because in this language I worked with commercial clusters and got to know it while writing my thesis",
          src: "java",
        },
        {
          id: 9,
          title: "Android",
          desc:
            "I have one year of commercial experience in programming applications for the android system.",
          src: "android",
        },
        {
          id: 10,
          title: "Github",
          desc:
            "I got to know the Github platform in college and from the beginning of creating projects I use it and put my work on it.",
          src: "github",
        },
      ],
      settings: {
        dots: true,
        dotsClass: "slick-dots",
        edgeFriction: 0.35,
        infinite: true,
        speed: 500,
        slidesToShow: 3,
        slidesToScroll: 3,
        responsive: [
          {
            breakpoint: 768,
            settings: {
              slidesToShow: 1,
              slidesToScroll: 1,
              infinite: true,
              dots: false,
            },
          },
        ],
      },
    };
  },
};
</script>
<style scoped lang="sass">
header
    text-align: center
    padding: 2vh 0
    font-size: 50px
    font-weight: bold
    font-family: 'Montserrat', sans-serif
    text-shadow: 2px 2px 4px #000000





.content
    margin-top: 5vh
    div.one-element
        padding: 0 30px

        h2
            padding-bottom: 3vh
            font-weight: 700
            font-size: 36px
            font-family: 'Montserrat', sans-serif

        div.for-desc
            position: relative

            h4
                padding-top: 20px
                text-align: center
                font-weight: 600
                font-family: 'Montserrat', sans-serif
        img
            width: 50%
            margin: 4vh auto



    h2
        text-align: center
</style>
