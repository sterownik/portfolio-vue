<template class="">
  <div>
    <div class=" col-lg-3   col-8 box">
      <img src="../assets/profile_photo.jpg" alt="" />
      <header>
        <p>
          Hi, I'm Wojciech Gołda and <br />
          I am developer
        </p>
        <h4 class="wordCarousel">
          <span
            >I worked with:
            <span class="toShow">{{ skillToShow }}</span>
          </span>
        </h4>
      </header>
    </div>
    <div class="links col-lg-3   col-8">
      <img
        :key="link.id"
        v-for="link in links"
        :src="require('@/assets/links/' + link.src + '.png')"
        @click="goToSite(link.link)"
        alt=""
      />
    </div>
    <div class="cono"></div>
  </div>
</template>
<script>
export default {
  methods: {
    goToSite(item) {
      window.location.href = item;
    },
  },
  mounted() {
    let i = 1;
    let that = this;

    setInterval(function() {
      that.skillToShow = that.skills[i];
      if (i === that.skills.length - 1) {
        i = 0;
      } else {
        i++;
      }
    }, 3000);
  },

  data() {
    return {
      links: [
        {
          id: 1,
          src: "cv",
          link:
            "https://sterownik.github.io/Portfolio_Wojciech_Golda/web/viewer.html?file=CV_Wojciech_Go%C5%82da.pdf",
        },
        { id: 2, src: "github", link: "https://github.com/sterownik" },
        {
          id: 3,
          src: "google-play",
          link:
            "https://play.google.com/store/apps/developer?id=Wojciech+Go%C5%82da",
        },
      ],

      skills: [
        "HTML",
        "CSS3/SASS",
        "JavaScript",
        "Vue.js",
        "React.js",
        "Bootstrap 4",
        "Firebase",
        "SQL",
        "Java",
        "Android",
        "Githube",
      ],
      skillToShow: "HTML",
    };
  },
};
</script>
<style scoped lang="sass">

$base-color: #E76F51
@-webkit-keyframes glow
     from
      color: #264653
      text-shadow: 0 0 10px $base-color, 0 0 20px $base-color, 0 0 30px $base-color, 0 0 40px $base-color, 0 0 50px $base-color, 0 0 60px $base-color, 0 0 70px $base-color, 0 0 90px $base-color
     to
      color:#264653
      text-shadow: 0 0 20px $base-color, 0 0 30px $base-color, 0 0 40px $base-color, 0 0 50px $base-color, 0 0 60px $base-color, 0 0 70px $base-color, 0 0 80px $base-color, 0 1 90px $base-color
@keyframes flip
    0%
        opacity: 0
    100%
        opacity: 1
.links
  height: 200px
  margin:20px auto
  justify-content: space-around
  display: flex

  img
    flex-basis: 30%
    cursor: pointer
    object-fit: contain
    transition: 0.5s
    height: 30%
    &:hover
      transform: scale(1.2)





.toShow
    animation: flip 3s 2.9s infinite
    display: block
    font-family: 'Montserrat', sans-serif
    padding-top: 10px
    text-shadow: 2px 2px #ddd
    font-weight: bold
    font-size: 28px
@keyframes textclip
    to
        background-position: 200% center
.flip4
    animation: flip4 10s cubic-bezier(0.23, 1, 0.32, 1.2) infinite
.box
    // height: 40vh
    padding: 30px 6px
    margin: 0 auto
    z-index: 2
    overflow: hidden
    top: 20%
    position: relative
    border-radius: 30px
    header
        top: 30%
        position: relative
        padding-top: 30px
        color: #14213d
        h4
            text-align: center
            font-family: 'Karla', sans-serif
        p
            text-align: center
            font-family: 'Karla', sans-serif
            font-size: 26px
    img
        width: 40%
        border-radius: 50%
        position: relative

        top: 10%
        left: 50%
        transform: translateX(-50%)
    &::after
        height: 100%
        content: ""
        z-index: -1
        width: 100%
        background-color: white
        opacity: 0.3
        filter: blur(10px)
        top: 0
        left: 0
        position: absolute
</style>
