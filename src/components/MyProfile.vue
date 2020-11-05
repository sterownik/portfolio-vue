<template>
  <div class="col-lg-7   col-11 box mx-auto">
    <img src="../assets/profile/logo_prz.png" alt="" />
    <div class="to-flex">
      <div>
        <h2>Studies</h2>
        <p>
          In 2016, I started engineering studies in
          <span>computer science</span> at the Rzeszów University of Technology
          to graduate in 2020 and receive an engineering diploma, from 2020, I
          <span>studying Masters</span> in Rzeszów University of Technology
        </p>
      </div>
      <div>
        <h2>Hobbies</h2>
        <p>
          I'm handball referee. In last handball season I become
          <span>referee in central level ZPRP</span> . Now I leading a matches
          in II league in Poland and some matches in Podkarpackie voivodeship
          both seniors and youth groups. Before that I was a
          <span>handball player</span> in Rzeszów
        </p>
      </div>
    </div>
    <div class="photos">
      <div>
        <img class="referee" src="../assets/profile/sedzia.jpg" alt="" />
      </div>

      <div>
        <img class="player" src="../assets/profile/zawodnik.jpg" alt="" />
      </div>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style scoped lang="sass">
div.box
  position: relative
  padding-bottom: 30px
  div.photos
    display: flex
    justify-content: space-between
    padding-bottom: 30px
    padding-top: 30px
    padding-left: 30px
    padding-right: 30px
    div
      flex-basis: 47%
      flex-wrap: wrap
      img.referee, img.player
        padding-top: 0
        width: 100%
        height: 40vh
        border-radius: 12%
        box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19)

        object-fit: cover








  div.to-flex
    display: flex
    padding: 3vh 20px 0 20px
    z-index: 2
    position: relative
    justify-content: space-between
    flex-wrap: wrap
    div
      flex-basis: 47%
      h2
        text-align: center
        color: #003C82
        font-style: oblique
        padding-bottom: 2vh
        text-transform: uppercase
      p
        font-family: 'Montserrat', sans-serif
        font-size: 24px
        text-align: justify
        span
          color: #003C82
          font-weight: bold

  img
    object-fit: cover
    position: relative
    padding-top: 3vh
    z-index: 2
    width: 100%
  &::after
    height: 100%
    content: ""
    width: 100%
    background-color: white
    border-radius: 30px
    opacity: 0.3
    top: 0
    left: 0
    position: absolute

@media (max-width: 767px)
  div.box
    div.photos
      display: flex
      justify-content: space-between
      flex-wrap: wrap
      div
        flex-basis: 100%
        padding-top: 30px
        img.referee, img.player
          width: 100%
          height: 40vh
          object-fit: cover
    div.to-flex
      div
        flex-basis: 100%
</style>
