<template lang="pug">
.outer-box
    h1.section-title 作者簡介
    p.en-title Artist Introduction
    br
    .full-row._between
        figure.full-col2
            //- img(src="~static/author/person.jpg")
            img.logo(src="~static/author/moubee.jpg")
        .author.full-col2
            dl
                dt 林政逸
                dd 林政逸(墨魂)，1962年生出生於嘉義，成長於嘉義。早年學習廣告設計，向李伍字、李伯男、曹根、郭彬源、藍再興、張碧寅、王儷容等老師學習西畫、水墨畫、美術設計。
                dd 書法受高中書法老師陳金詮啟蒙臨帖觀念後，自學歷代碑帖、書論，獲益於前人書跡。潛修書法多年，熟知各種書體的歷史發展，並專精行、草書寫。書法作品高曠豪壯，取各家之長而能自開新意。水墨則帶空靈之美，讓觀者興起無限遐思。
                dd 在傳統藝術之美逐漸式微的今日，長期而不間斷地推廣書法美學。創辦『墨魂書畫院』，以小班教學方式，傳習書法藝術之美。1995年迄今，多次擔任本校學生社團『書法研學社』指導老師，開設指導課程，並協助學生舉辦成果展與研究展。林政逸亦掌握時代趨勢，建構『墨魂書畫院』網站，突破時間及地域限制，分享在研習書法藝術上的見解。
    hr
    .full-row._between
        figure.full-col2
            img.logo(src="~static/author/moubee.jpg")
        .author.full-col2
            dl
                dt 得獎紀錄暨個人經歷
                dd.award 作品多次入選全省美展、全國油畫展、桃城美展、台南市美展。
                dd.award 獲邀參展全國名家聯展及嘉義市文化局百號油畫展。
                dd.award 曾任中國生產力中心講師。
                dd.award 擔任中正大學書法研學社指導老師、顧問、評審多屆。
                dd.award 嘉義市墨文藝術家協會學術顧問。
                dd.award 編寫『漢隸研習指南』一書，提供有志自學漢隸書寫之人學習管道。
    

</template>

<style lang="sass">
figure
    img
        width: 100%
        max-width: 100%
.author
    dl
        text-align: left
        
        dt
            font-size: 1.25em
            font-weight: 700
            margin-bottom: 0.25em
        dd
            font-size: 1em
            margin-top: 0.2em
            text-indent: 1.5em
            &.award
                margin-left: 1em
                text-indent: -1em
            &.award:before
                content: "◆"
                font-size: 0.5em

</style>
