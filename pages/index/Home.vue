<template lang="pug">
.rightblock
  swiper(:options="swiperOption" ref="mySwiper" @someSwiperEvent="callback")
    swiper-slide
      img(src="~static/home-img/banner01.jpg")
    swiper-slide
      img(src="~static/home-img/banner02.jpg")
    swiper-slide
      img(src="~static/home-img/banner03.jpg")
    .swiper-pagination(slot="pagination")
  br
  br
  h1.section-title 書藝創作理念
  p.en-title About Calligraphy Artsworks
  section.home-about
    h3 「從前世到今生，我只知道手中握的筆未曾輕放，用我深刻的靈魂，揮灑出每一筆」。
    p 墨魂，是林政逸老師的書畫字號，也是他在藝術創作上的書畫理念。習藝數十載，林老師每日不懈於創作精進自我，對藝術的堅持、熱愛及理念，一筆一畫呈現在作品之中。以墨入魂，正是林老師在創作上的寫照。

  //- .index-image

</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'

export default {
  components: {
    swiper,
    swiperSlide
  },
  name: 'carrousel',
  data() {
    return {
      swiperOption: {
        loop: true,
        pagination : {
          el: '.swiper-pagination',
          clickable:true,
        },
        speed: 1500,
        autoplay: {
          stopOnLastSlide: false,
          delay: 5000,
        },
        effect : 'fade',
        fadeEffect:{
          crossFade: true,
        },
        
        
      }
    }
    
  },
  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="sass">
.rightblock
  width: 100%
  margin: 0
  padding: 0

.home-about
  padding: 2em 4em
  text-align: center
  h3
    font-family: 'cwTeXMing'
    letter-spacing: 0.25em
  p
    font-weight: 400
    padding-top: 2em

.swiper-container
  max-width: calc(100vw - 200px)
  overflow: visible
@media screen and (max-width: 1050px)
  .swiper-container
    max-width: 100%
    padding-top: 46px

.swiper-slide img
  max-width: 100%
  width: 100%
.swiper-pagination
  bottom: -20px!important
.swiper-pagination-bullet
  background: #9b7a66
  margin: 10px
.swiper-pagination-bullet-active
  background: #6d5a50
</style>
