<template lang="pug">
.outer-box
    h1.section-title 聯絡方式
    p.en-title Contact Us
    .full-row._between
        figure.full-col2.linkbox
            a(href="https://www.facebook.com/pg/InkSpirit2017/photos/?ref=page_internal", target="_blank")
                img(src="~static/FB_link.jpg", alt="墨魂書法藝術館")
        .full-col2.txtbox
            //- font-awesome-icon(:icon="['fab', 'facebook-square']" size="2x")
            h3.link-title 墨魂（林政逸）書法藝術館
            p 設於Facebook的粉絲專頁。
    hr
    .full-row._between
        figure.full-col2.linkbox
            a(href="https://goo.gl/forms/RtmKL9mlJpKOhDJl1",target="_blank")
                img(src="~static/author/moubee.jpg", alt="墨魂書法藝術館")
        .full-col2.txtbox
            h3.link-title 書法課程報名
            p 提供給有學習意願者的線上報名單。
    hr
</template>

<script>
export default {

}
</script>

<style lang="sass">
.linkbox
    height: 120px
    img
        position: relative
        max-width: 100%
        top: -50%

.txtbox
    display: flex
    flex-direction: column
    align-content: center
    justify-content: center
.link-title
    padding-left: 0.5em
    font-size: 1.25em
    font-weight: 700
    vertical-align: 0.25em

</style>