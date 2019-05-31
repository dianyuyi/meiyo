<template lang="pug">
.rightblock
	swiper(:options="swiperOption" ref="mySwiper" @someSwiperEvent="callback")
		swiper-slide
			img(src="~assets/book/banner/h-01.png")
		swiper-slide
			img(src="~assets/book/banner/h-01.png")
		.swiper-pagination(slot="pagination")
	br
	br
	img.line-br(src="~assets/book/line.png")
	.outer-box
		h1.section-title 現正熱銷
		p.en-title Hot Sales
		.full-row._between
			figure.full-col3.booksbox(v-for="book in hotList")
				//- a.booklink(:href="book.link",target="_blank")
				.hot 
					span HOT!
				img.topic(:src="require(`~/assets/${book.img}`)")
				h3.booktitle {{ book.title }}
				span.price-default(v-if="book.discount<100") $ {{ book.price }}
				p.price-discount(:class="{ red: book.discount<100 }") $ {{ parseInt( book.price*(book.discount/100) ) }}
				.discount-tip(v-if="book.discount<100")
					p {{ book.discount }}折
				//- p.booktext {{ book.description}}
		.full-row
			.read-more
				nuxt-link(to="/Works")
					span 閱讀更多

		h1.section-title 新書上架
		p.en-title New Books
		.full-row._between
			figure.full-col4.booksbox(v-for="book in booksList")
				//- a.booklink(:href="book.link",target="_blank")
				img.topic(:src="require(`~/assets/${book.img}`)")
				h3.booktitle {{ book.title }}
				//- p.booktext {{ book.description}}
				span.price-default(v-if="book.discount<100") $ {{ book.price }}
				p.price-discount(:class="{ red: book.discount<100 }") $ {{ parseInt( book.price*(book.discount/100) ) }}
				.discount-tip(v-if="book.discount<100")
					p {{ book.discount }}折
		.full-row
			.read-more
				nuxt-link(to="/Works")
					span 閱讀更多

	Footer

	//- .index-image

</template>

<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import Footer from '@/components/footer'

export default {
	components: {
		swiper,
		swiperSlide,
		Footer
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
			},
			hotList: 
				[
					{
						title: '詭影',
						description: '鬼故事天王又一全新力作！夜深人靜時，是否也曾有竊竊夜語在你耳畔響起⋯⋯',
						author: '陳為民',
						img: 'book/poster/01.jpg',
						discount: 79,
						price: 230
					},
					{
						title: '書法案上有隻喵',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/02.jpg',
						discount: 79,
						price: 230
					},
					{
						title: '薄雨',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/03.jpg',
						discount: 79,
						price: 230
					},
				],
			booksList: 
				[
					{
						title: '詭影',
						description: '鬼故事天王又一全新力作！夜深人靜時，是否也曾有竊竊夜語在你耳畔響起⋯⋯',
						author: '陳為民',
						img: 'book/poster/01.jpg',
						discount: 79,
						price: 230
					},
					{
						title: '書法案上有隻喵',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/02.jpg',
						discount: 79,
						price: 230
					},
					{
						title: '薄雨',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/03.jpg',
						discount: 100,
						price: 230
					},
					{
						title: '籠內的獅子',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/04.jpg',
						discount: 88,
						price: 230
					},
					{
						title: '粗食潮流',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/05.jpg',
						discount: 79,
						price: 230
					},
					{
						title: '業之扉-KARMA-',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/06.jpg',
						discount: 100,
						price: 230
					},
					{
						title: '機翼下的薄螢：航道區域生態調查手札',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/07.png',
						discount: 88,
						price: 230
					},
					{
						title: '匯聚之絲',
						description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
						author: '枚酉',
						img: 'book/poster/08.png',
						discount: 79,
						price: 230
					},
					// {
					// 	title: '書法初學者易犯的謬誤大哉問',
					// 	description: '誰說喵爪就握不了筆？且看喵爪如何大筆一揮，寫出精采書藝！',
					// 	author: '枚酉',
					// 	img: 'book/poster/09.png',
					// 	discount: 79,
					// 	price: 230
					// },
				]
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
	// max-width: 1252px
	margin: 0 auto
	margin-top: 100px
	padding: 0


.swiper-container
	max-width: 80vw
	overflow: visible!important
.swiper-slide img
	max-width: 100%
	width: 100%
	// max-height: 360px
.swiper-pagination
	bottom: -20px!important
.swiper-pagination-bullet
	background: #9b7a66
	margin: 10px
.swiper-pagination-bullet-active
	background: #6d5a50

.line-br
	max-width: 80vw
	width: 100%

.booksbox
	display: flex
	justify-content: center
	align-items: center
	margin-bottom: 2.5em
	flex-direction: column
	position: relative
	height: 320px
	overflow: hidden
	transition: 0.5s
	background-color: #fff
	> *
		transition: 0.5s
	.booktitle,.booktext
		z-index: 2
	.booktitle
		font-size: 1rem
		opacity: 0.5
		margin-top: 15px
	.booktext
		font-size: 0.875rem
		opacity: 0
		width: 0
		height: 0
	.topic
		z-index: 0
		height: 60%
		max-width: 100%
		box-shadow: 3px 2px 20px rgba(black,0.1)
	.price
		&-default
			text-decoration: line-through
		&-discount
			&.red
				color: red
				font-weight: 900
	.hot
		position: absolute
		left: -50px
		top: -50px
		z-index: 3
		width: 220px
		height: 30px
		color: #fff
		background-color: #ff3321
		opacity: 1
		span
			height: 30px
			font-size: 1.25rem
			font-weight: 700
	.discount-tip
		position: absolute
		right: -50px
		bottom: 70px
		border-radius: 50% 50% 50% 0
		padding: 5px 0
		width: 50px
		height: 50px
		background: #ffd263
		transform: rotate(-45deg)

	&:hover
		background-color: rgba(255,248,230,0.2)
		border: solid 1px #eee
		.booktitle,.booktext
			opacity: 1
		.booktitle
			margin-top: 8px
			font-size: 1.2rem
			line-height: 1.1
		.booktext
			width: 100%
		.topic
			z-index: 2
			height: 70%
		.hot
			transform: rotate(-45deg)
			top: 40px
		.discount-tip
			right: 10px
			bottom: 10px
			z-index: 4
			transform: rotate(45deg)
			p
				transform: rotate(-45deg)
				position: relative
				top: 10px
		.price
			&-default
				font-size: 0.875rem
			&-discount
				font-size: 1.25rem

@media screen and (max-width: 1050px)
	.rightblock
		margin-top: 40px
	.swiper-container
		max-width: 100vw
		padding-top: 0px
		display: none
	.line-br
		max-width: 100vw
</style>
