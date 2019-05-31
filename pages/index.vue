<template lang="pug">
  //- .container
  //-   .left
  //-     nuxt-link(to="/") index
  //-     nuxt-link(to="/home") home
  //-   .right
  //-     nuxt-child(:key="$route.params.id")
  #app
    headroom
      header.header
        div.logo-mb-space
          nuxt-link.logo-mb(to="/Home")
        .navbar
          ul.nav-left
            li
              nuxt-link(to="/Works") 書籍
            li
              nuxt-link(to="/Works") 雜誌
            li
              nuxt-link(to="/Works") 漫畫
            li
              nuxt-link(to="/Works") 電子書
            li
              nuxt-link(to="/Works") 影音專區
          ul.nav-right
            li
              nuxt-link(to="/Home") 登入
            li
              nuxt-link(to="/Home") 會員中心 
                i.fa.fa-info-circle
      Slide(right noOverlay width="200")
        nuxt-link(to="/Home")
          span 回首頁
        nuxt-link(to="/Works")
          span 書籍
        nuxt-link(to="/Works")
          span 雜誌
        nuxt-link(to="/Works")
          span 漫畫
        nuxt-link(to="/Works")
          span 電子書
        nuxt-link(to="/Works")
          span 影音專區
        nuxt-link(to="/Works")
          span 登入
        nuxt-link(to="/Works")
          span 會員中心
    
    .mainblock
    transition(name="fade" mode="out-in")
      nuxt-child(:key="$route.params.id")
    


</template>

<script>
import { headroom } from 'vue-headroom'
import{ Slide } from 'vue-burger-menu'

export default {
  name: 'App',
  components: {
    headroom, 
    Slide,
  },
}
</script>

<style lang="sass">

@import "swiper/dist/css/swiper.css"
@import url(https://fonts.googleapis.com/earlyaccess/cwtexming.css)

html, body, div, span, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
abbr, address, cite, code,
del, dfn, em, img, ins, kbd, q, samp,
small, strong, sub, sup, var,
b, i,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, dialog, figure, main, footer, header,
hgroup, menu, nav, section,
time, mark, audio, video
  margin: 0
  padding: 0
  border: 0
  outline: 0
  box-sizing: border-box

body
  font-size: 14px
  line-height: 1.5
  letter-spacing: 0.06em
  color: #534741

#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif, serif, 'cwTeXMing'
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  display: flex
  width: 100%
  text-align: center
  margin: 0px
  padding: 0px
  
// Header
.headroom
  background-color: #f8f8f8

.header
  opacity: 1
  line-height: 60px
  padding: 0px 20px
  margin: 0 auto
  max-width: 1252px
  background-color: #f8f8f8
  border-bottom: solid 2px #eee
  // background-color: rgba(255, 255, 255, 0.94)
  text-align: left
  display: flex
  .logo-mb-space
    width: 240px
    // margin: 0 auto
    .logo-mb
      display: block
      height: 60px
      background-color: #222
      background-image: url(~static/meiyou_w.png)
      background-size: 80%
      background-repeat: no-repeat
      background-position: center center
      text-align: left

  .navbar
    display: flex
    width: 100%
    justify-content: space-around
    ul
      display: flex
      list-style: none
      li
        font-weight: 900
        color: #222
        margin-left: 20px
        transition-duration: 0.2s
        a
          text-decoration: none
          color: #222
        &:hover
          transform: translate(0px,2px)
          cursor: pointer
          opacity: 0.8
      &.nav-left
        li > a
          padding-right: 20px
          position: relative
          &:after
            content: "▼"
            position: absolute

        
@media screen and (max-width: 1050px)
  .header
    opacity: 1
    padding-left: 0
    height: 60px
    display: block
    .logo-mb-space
      opacity: 1
    .navbar
      opacity: 0
      display: none
@media screen and (max-width: 500px)
  .header
    .logo-mb-space
        // margin: 0 auto 0 5px


// Mobile-nav
.bm-burger-button
  position: fixed
  width: 24px
  height: 18px
  left: 20px
  top: 16px
  cursor: pointer
@media screen and (min-width: 1050px)
  .bm-burger-button
    display: none

.bm-burger-bars
  background-color: #534741

.line-style
  position: absolute
  height: 10%
  left: 0
  right: 0

.cross-style
  position: absolute
  top: 24px
  right: 40px
  cursor: pointer

.bm-cross
  background: #534741

.bm-cross-button
  height: 30px
  width: 30px

.bm-menu
  height: 100vh /* 100% Full-height */
  width: 0 /* 0 width - change this with JavaScript */
  position: fixed /* Stay in place */
  z-index: 1000 /* Stay on top */
  top: 0
  left: 0
  background-color: transparent
  background-image: url(~static/paper_bg.png)
  background-size: 200% 100%
  background-position: left -15px
  background-repeat: no-repeat
  overflow-x: hidden /* Disable horizontal scroll */
  padding-top: 40px /* Place content 60px from the top */
  transition: 0.5s /*0.5 second transition effect to slide in the sidenav*/

.bm-overlay
  background: rgba(0, 0, 0, 0.3)

.bm-item-list
  color: #534741
  margin-left: 25%
  font-size: 1rem

.bm-item-list > *
  display: flex
  text-decoration: none
  min-width: 120px
  padding: 1em 0 0.25em 0
  color: #534741
  transition: .5s
  &:hover
    transform: translate(10px,-2px)
    border-bottom: 2px dotted #534741
    & > span:after
      transition: .5s
      opacity: 1

.bm-item-list > * > span
  margin-left: 10px
  font-weight: 500
  color: #534741
  &:after
    content: "➤"
    padding-left: 0.5em
    opacity: 0
    


// Index logo
.web-logo
  position: relative
  top: 30px
  display: block
  height: 300px
  padding-top: 40px
  .logo
    display: block
    height: 250px
    width: 100%
    opacity: 1
    background-image: url(~static/meiyou.png)
    background-size: contain
    background-repeat: no-repeat
    background-position: center bottom

// Route
.linklist
  position: absolute
  top: 380px
  left: 0
  width: 100%
  list-style: none
  padding-left: 0
  .link-item
    position: relative
    margin-top: -1px
    background-color: #fff
    transition: .5s
    &:hover
      background-color: #f7f5f4
    &:before
      content: ""
      position: absolute
      top: 0
      left: 50%
      width: 150px
      transform: translateX(-50%)
      height: 1px
      background-color: #f7f5f4
    a
      display: block
      padding: 10px
      color: #6d5a50
      font-size: 0.875em
      text-decoration: none
      align-items: center

</style>
