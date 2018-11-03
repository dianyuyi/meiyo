<template lang="pug">
.outer-box
    h1.section-title 近期活動
    p.en-title Recent Activities
    .full-row._between
        figure.full-col2.newsbox
            img.topic(src="~static/active/active01.jpg")
        .full-col2.active
            h3 中正大學-社團指導課程
            p 每週三於中正大學社團相關活動教室進行，以社團學生為主進行書法在筆法技巧或佈局章法的指導教學。
    hr
    .full-row._between
        figure.full-col2.newsbox
            img.topic(src="~static/active/active02.jpg")
        .full-col2.active
            h3 書法教室-小班制書法教學
            p 由林老師於自宅開班授課的專業書法教學，以少人數的小班制為主，以達到更全面及更專精的授課效果。
                //- a(href="https://goo.gl/forms/RtmKL9mlJpKOhDJl1",target="_blank") 報名課程
    hr
</template>

<style lang="sass">
.newsbox
    position: relative
    border: 1px solid #eee
    height: 200px
    overflow: hidden
    .topic
        position: absolute
        left: 0
        top: -25%
        width: 100%
        align-items: center
        transition: 1s
        &:hover
            transform: scale(1.2)

.active
    text-align: left
    h3
        padding: 1em 0
    // a
    //     display: inline-block
    //     padding: 2px 10px
    //     font-size: 0.75rem
    //     border-radius: 5px
    //     background-color: #534741
    //     color: #fff
    //     border: 1px solid #534741
    //     text-decoration: none
    //     transition: 0.3s
    //     &:hover
    //         background-color: #fff
            
    //         padding: 2px 10px
    //         color: #534741
</style>