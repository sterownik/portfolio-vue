<template>
  <div>
    <div class="up">
      <span>{{ toUp }}</span>
      <img @click="changeComponent('up')" src="../assets/up-arrow.png" alt="" />
    </div>
    <div class="down">
      <span>{{ toDown }}</span>
      <img
        @click="changeComponent('down')"
        src="../assets/down-arrow.png"
        alt=""
      />
    </div>
  </div>
</template>
<script>
export default {
  inject: ["changeTabs"],
  props: ["toUp", "toDown"],
  methods: {
    changeComponent(direction) {
      this.changeTabs(direction);
    },
  },
};
</script>
<style lang="sass" scoped>


div
    div
        position: fixed
        opacity: 0.7

        right: 5vh
        img
            width: 85px
            cursor: pointer

        span
            font-size: 22px
            padding: 10px
            color: #fff
            display: inline
        .up
            top: 5vh
            transition: 0.5s
            &:active
              top: 1vh


        .down
            bottom: 5vh
            transition: 0.5s
            &:active
              bottom: 1vh


@media (max-width: 769px)
  div
    div
        right: 10px
        img
          width: 65px
        span
          display: none

@media (max-width: 767px)
  div
    div
        right: 10px
        img
            width: 35px
        span
          display: none
</style>
