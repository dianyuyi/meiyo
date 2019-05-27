<template lang="pug">
.outer-box
    h1.section-title 作品概覽
    p.en-title Calligraphy works
    .full-row._around
        gallery(:images="workslist" :index="index" @close="index = null")
        .image(v-for="(image, imageIndex) in workslist" :key="imageIndex" @click="index = imageIndex" :style="{ backgroundImage: 'url(' + `${image.href}` + ')', width: '150px', height: '150px' }")
</template>


<script>
import VueGallery from 'vue-gallery';
export default {
    data(){
        return {
            workslist: [
            {
                title: '從容無為',
                description: '70x135cm 四尺對開橫幅',
                href: require(`~/assets/works/01.jpg`)
            },
            {
                title: '啼鳥雲山靜，落花溪水香',
                description: '135x35x2cm 條幅對聯',
                href: require(`~/assets/works/02.jpg`)
            },
            {
                title: '行書錄李白詩二首橫幅-局部一',
                description: '局部放大',
                href: require(`~/assets/works/03.jpg`)
            },
            {
                title: '行書錄李白詩二首橫幅-局部二',
                description: '局部放大',
                href: require(`~/assets/works/04.jpg`)
            },
            {
                title: '行書錄李白詩二首橫幅-局部三',
                description: '局部放大',
                href: require(`~/assets/works/05.jpg`)
            },
            {
                title: '行書錄李白詩二首橫幅',
                description: '135x35cm 四尺對開橫幅',
                href: require(`~/assets/works/06.jpg`)
            },
            {
                title: '鏤月裁雲',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/07.jpg`)
            },
            {
                title: '見素抱樸',
                description: '35x135cm 四尺對開橫幅',
                href: require(`~/assets/works/08.jpg`)
            },
            {
                title: '施潤章山行',
                description: '70x135cm 四尺全開中堂',
                href: require(`~/assets/works/09.jpg`)
            },
            {
                title: '山行',
                description: '抽象水墨',
                href: require(`~/assets/works/10.jpg`)
            },
            {
                title: '鶴鳴九皋',
                description: '35x135cm 四尺對開橫幅',
                href: require(`~/assets/works/11.jpg`)
            },
            {
                title: '鴻鵠凌虛',
                description: '35x135cm 四尺對開橫幅',
                href: require(`~/assets/works/12.jpg`)
            },
            {
                title: '康有為詩句草書、行書條幅',
                description: '135x35x2cm 四尺對開條幅',
                href: require(`~/assets/works/13.jpg`)
            },
            {
                title: '小品三件-幽懷得春氣、脩竹引清風、純篤',
                description: '70cm 行書、魏碑、隸書小品',
                href: require(`~/assets/works/14.jpg`)
            },
            {
                title: '幽懷、修竹行書五言聯',
                description: '135x35x2cm 四尺對開對聯',
                href: require(`~/assets/works/15.jpg`)
            },
            {
                title: '落花舞秋',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/16.jpg`)
            },
            {
                title: '春逐鳥聲開-現代書藝行書',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/17.jpg`)
            },
            {
                title: '守卓禪師七言律詩',
                description: '38x26.5cm 行書小品',
                href: require(`~/assets/works/18.jpg`)
            },
            {
                title: '黃龍道震禪師禪偈',
                description: '135x35cm 四尺對開四條屏',
                href: require(`~/assets/works/19.jpg`)
            },
            {
                title: '茶韻',
                description: '19.5x13.5cm(畫心部分) 行書小品',
                href: require(`~/assets/works/20.jpg`)
            },
            {
                title: '吐言落筆魏碑五言聯',
                description: '135x35x2cm 四尺對開對聯',
                href: require(`~/assets/works/21.jpg`)
            },
            {
                title: '龍門清遠禪師行書中堂',
                description: '135x760m 四尺全開中堂(略窄)',
                href: require(`~/assets/works/22.jpg`)
            },
            {
                title: '魯迅句大字魏碑條幅',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/23.jpg`)
            },
            {
                title: '李白詩句大字魏碑條幅',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/24.jpg`)
            },
            {
                title: '閑來喫茶',
                description: '小品橫幅',
                href: require(`~/assets/works/25.jpg`)
            },
            {
                title: '水墨白荷',
                description: '荷葉羅裙一色裁，芙蓉向臉南邊開。亂入池中看不見，聞歌始覺有人來。',
                href: require(`~/assets/works/26.jpg`)
            },
            {
                title: '曲江春望-魏碑橫幅',
                description: '55x135cm 橫幅',
                href: require(`~/assets/works/27.jpg`)
            },
            {
                title: '曲江春望-草書條幅',
                description: '135x35cm 四尺對開條幅',
                href: require(`~/assets/works/28.jpg`)
            },
            {
                title: '東坡詩暨李白詩行書中堂',
                description: '135x70cm 四尺全開中堂',
                href: require(`~/assets/works/29.jpg`)
            },
            {
                title: '鶴沖天',
                description: '70cm 小品',
                href: require(`~/assets/works/30.jpg`)
            }
            ],
            index: null
        }
    },
    components:{
        'gallery': VueGallery
    }
}
</script>

<style lang="sass">
.image
    display: inline-flex
    background-size: cover
    background-repeat: no-repeat
    background-position: center center
    background-color: #ebebeb
    border: 1px solid #ebebeb
    margin: 5px

.blueimp-gallery > .description
    text-shadow: 0px 0px 2px #000
    font-weight: 700
    top: 40px!important
    opacity: 0.8

</style>