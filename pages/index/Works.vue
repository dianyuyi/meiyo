<template lang="pug">
.outer-box
    h1.section-title 作品概覽
    p.en-title Calligraphy works
    .full-row._around
        gallery(:images="workslist" :index="index" @close="index = null")
        .image(v-for="(image, imageIndex) in workslist" :key="imageIndex" @click="index = imageIndex" :style="{ backgroundImage: 'url( ' + image.href + ')', width: '150px', height: '150px' }")
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
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/23376273_130470757668378_2849046244635345331_n.jpg?_nc_cat=101&_nc_ht=scontent.ftpe8-3.fna&oh=09c691b0e4a3e2f82ec60ee6b025aefa&oe=5C7753A0'
            },
            {
                title: '啼鳥雲山靜，落花溪水香',
                description: '135x35x2cm 條幅對聯',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/23472038_130011911047596_7189349392148394266_n.jpg?_nc_cat=100&_nc_ht=scontent.ftpe8-3.fna&oh=354e73bdb492c3befb09eeb2c478bbde&oe=5C3DA265',
            },
            {
                title: '行書錄李白詩二首橫幅-局部一',
                description: '局部放大',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/42860142_252757335439719_9208277528911806464_o.jpg?_nc_cat=111&_nc_ht=scontent.ftpe8-3.fna&oh=f5d9b378641121ef616697ec5cabf44b&oe=5C475ABD',
            },
            {
                title: '行書錄李白詩二首橫幅-局部二',
                description: '局部放大',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/42767815_252757308773055_528959139859136512_n.jpg?_nc_cat=102&_nc_ht=scontent.ftpe8-4.fna&oh=956a851efd1453d4016833ecd7d0fe7f&oe=5C83AF87',
            },
            {
                title: '行書錄李白詩二首橫幅-局部三',
                description: '局部放大',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/42838548_252757285439724_4638224020053950464_n.jpg?_nc_cat=106&_nc_ht=scontent.ftpe8-3.fna&oh=805f07857539002ccf86e3dab41d6cf3&oe=5C744818',
            },
            {
                title: '行書錄李白詩二首橫幅',
                description: '135x35cm 四尺對開橫幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/42885652_252757245439728_8585485920709378048_n.jpg?_nc_cat=105&_nc_ht=scontent.ftpe8-3.fna&oh=00bb5bed95e0483314ff6b2b00781312&oe=5C4A9897',
            },
            {
                title: '鏤月裁雲',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/42089527_249413275774125_95514536450195456_n.jpg?_nc_cat=101&_nc_ht=scontent.ftpe8-3.fna&oh=52de8ba39c047ca11223de1b27ff77e8&oe=5C7FEE4D',
            },
            {
                title: '見素抱樸',
                description: '35x135cm 四尺對開橫幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/42246760_249413242440795_7583400158549770240_n.jpg?_nc_cat=105&_nc_ht=scontent.ftpe8-3.fna&oh=966ddecdf5779c189088547c6f564165&oe=5C453AF9',
            },
            {
                title: '施潤章山行',
                description: '70x135cm 四尺全開中堂',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/41447949_246759332706186_4938095664543301632_n.jpg?_nc_cat=106&_nc_ht=scontent.ftpe8-3.fna&oh=6339566f754ae5c2f02aa0f89208bc1b&oe=5C3DD95D',
            },
            {
                title: '山行',
                description: '抽象水墨',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/41426703_246759299372856_2782986551217356800_n.jpg?_nc_cat=106&_nc_ht=scontent.ftpe8-3.fna&oh=24ea679f9914784a976c17b594a06ced&oe=5C89B63C',
            },
            {
                title: '鶴鳴九皋',
                description: '35x135cm 四尺對開橫幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/41409130_246746209374165_985085749026095104_n.jpg?_nc_cat=111&_nc_ht=scontent.ftpe8-3.fna&oh=8b05d5b9edbe434f124c3cc580ea58ce&oe=5C7F9A8E',
            },
            {
                title: '鴻鵠凌虛',
                description: '35x135cm 四尺對開橫幅',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/41398861_246746192707500_256235962172964864_n.jpg?_nc_cat=104&_nc_ht=scontent.ftpe8-4.fna&oh=5184ae04aa30f1d0fd04f50a28abc42f&oe=5C798B2C',
            },
            {
                title: '康有為詩句草書、行書條幅',
                description: '135x35x2cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-1.fna.fbcdn.net/v/t1.0-9/40188026_242347869813999_4017635790203912192_n.jpg?_nc_cat=109&_nc_ht=scontent.ftpe8-1.fna&oh=9a27cda6353c4997bd9d0caf604b3b72&oe=5C751F2C',
            },
            {
                title: '小品三件-幽懷得春氣、脩竹引清風、純篤',
                description: '70cm 行書、魏碑、隸書小品',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/39515077_239437893438330_1058311093132197888_n.jpg?_nc_cat=105&_nc_ht=scontent.ftpe8-3.fna&oh=afb896480828dc4f6460f8e471b9f167&oe=5C84B758',
            },
            {
                title: '幽懷、修竹行書五言聯',
                description: '135x35x2cm 四尺對開對聯',
                href: 'https://scontent.ftpe8-1.fna.fbcdn.net/v/t1.0-9/39851662_239431130105673_2260002681529565184_n.jpg?_nc_cat=109&_nc_ht=scontent.ftpe8-1.fna&oh=8fda7695004007376381c8307567071d&oe=5C87B467',
            },
            {
                title: '落花舞秋',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/38624573_226641238051329_5269693141526511616_n.jpg?_nc_cat=111&_nc_ht=scontent.ftpe8-3.fna&oh=9897d69aa7d6114adfb74c26a746ef36&oe=5C796706',
            },
            {
                title: '春逐鳥聲開-現代書藝行書',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/38481189_226641188051334_8189331108127571968_n.jpg?_nc_cat=100&_nc_ht=scontent.ftpe8-3.fna&oh=201a3ef641c48bbed2a633b0545be3e3&oe=5C8A67FD',
            },
            {
                title: '守卓禪師七言律詩',
                description: '38x26.5cm 行書小品',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/37877612_216749969040456_4835133298319556608_n.jpg?_nc_cat=107&_nc_ht=scontent.ftpe8-3.fna&oh=832ca20158a7110fac35893218f2042f&oe=5C7D4CC7',
            },
            {
                title: '黃龍道震禪師禪偈',
                description: '135x35cm 四尺對開四條屏',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/36750441_200854757296644_3506687222038396928_n.jpg?_nc_cat=105&_nc_ht=scontent.ftpe8-3.fna&oh=11df4520d1adf3fb09103de8410ec911&oe=5C82B359',
            },
            {
                title: '茶韻',
                description: '19.5x13.5cm(畫心部分) 行書小品',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/36240656_193315748050545_794347711699615744_n.jpg?_nc_cat=102&_nc_ht=scontent.ftpe8-4.fna&oh=14faed5858cd1b06237e459b2fc084f6&oe=5C4118BA',
            },
            {
                title: '吐言落筆魏碑五言聯',
                description: '135x35x2cm 四尺對開對聯',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/34531478_181604122555041_7006639093543075840_n.jpg?_nc_cat=110&_nc_ht=scontent.ftpe8-4.fna&oh=6ea2d5ad5c1df2ac745def7875b4ba53&oe=5C817D89',
            },
            {
                title: '龍門清遠禪師行書中堂',
                description: '135x760m 四尺全開中堂(略窄)',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/34442898_181599002555553_3101884101964070912_n.jpg?_nc_cat=104&_nc_ht=scontent.ftpe8-4.fna&oh=6579029967a524157664ebbd22a12464&oe=5C3D0F58',
            },
            {
                title: '魯迅句大字魏碑條幅',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/34482487_181593052556148_3626992399915417600_n.jpg?_nc_cat=103&_nc_ht=scontent.ftpe8-3.fna&oh=485599749e741b3dd6f66a429108cafb&oe=5C8365FE',
            },
            {
                title: '李白詩句大字魏碑條幅',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/34501199_181593042556149_6947885706165354496_n.jpg?_nc_cat=111&_nc_ht=scontent.ftpe8-3.fna&oh=91e43692f27f198461b00903ae65bac1&oe=5C778BFD',
            },
            {
                title: '閑來喫茶',
                description: '小品橫幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/33828799_179684539413666_3646746986029252608_n.jpg?_nc_cat=106&_nc_ht=scontent.ftpe8-3.fna&oh=1cd6a2c073dacf3da4d7e23507c715b7&oe=5C81936E',
            },
            {
                title: '水墨白荷',
                description: '荷葉羅裙一色裁，芙蓉向臉南邊開。亂入池中看不見，聞歌始覺有人來。',
                href: 'https://scontent.ftpe8-1.fna.fbcdn.net/v/t1.0-9/33899662_179680409414079_1210723552433537024_n.jpg?_nc_cat=109&_nc_ht=scontent.ftpe8-1.fna&oh=9529342b953e2c0676f962e1a45a9a09&oe=5C436865',
            },
            {
                title: '曲江春望-魏碑橫幅',
                description: '55x135cm 橫幅',
                href: 'https://scontent.ftpe8-3.fna.fbcdn.net/v/t1.0-9/32972203_177495136299273_4855550387433766912_n.jpg?_nc_cat=106&_nc_ht=scontent.ftpe8-3.fna&oh=a07b8f5a9594deb9705a43b3462071d3&oe=5C832A0E',
            },
            {
                title: '曲江春望-草書條幅',
                description: '135x35cm 四尺對開條幅',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/32942369_177495129632607_426901620165443584_n.jpg?_nc_cat=102&_nc_ht=scontent.ftpe8-4.fna&oh=075839aaa104d74f28a3a0ce6c05bbc1&oe=5C42722D',
            },
            {
                title: '東坡詩暨李白詩行書中堂',
                description: '135x70cm 四尺全開中堂',
                href: 'https://scontent.ftpe8-4.fna.fbcdn.net/v/t1.0-9/32294143_175639613151492_7088952713001566208_n.jpg?_nc_cat=104&_nc_ht=scontent.ftpe8-4.fna&oh=5c373617f0ec9008d062a588b0d257c7&oe=5C3D5E8E',
            },
            {
                title: '鶴沖天',
                description: '70cm 小品',
                href: 'https://scontent.ftpe8-2.fna.fbcdn.net/v/t1.0-9/31948324_173955703319883_939006823023771648_n.jpg?_nc_cat=103&_nc_ht=scontent.ftpe8-2.fna&oh=75717dcbb8b617686792b6068f7a42d7&oe=5C7BE3A8',
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