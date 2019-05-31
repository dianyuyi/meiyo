<template lang="pug">
.rightblock
	.outer-box
		.full-row._around
			.depart-col-30
				.type-box(v-for="type in typesList")
					.panel-title
						p {{ type.typename}}
					.panel-child(v-for="list in type.childtype")
						p {{list.name}}

			.depart-col-70
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

	Footer

</template>

<script>
import Footer from '@/components/footer'

export default {
	components: {
		Footer
	},
	data() {
		return {
			typesList: 
				[
					{
						typename: '書籍',
						childtype: [
							{name: '中文書'},
							{name: '外文書'}
						],
					},
					{
						typename: '雜誌',
						childtype: [
							{name: '中文雜誌'},
							{name: '日文MOOK'},
							{name: '歐美雜誌'}
						],
					},
					{
						typename: '雜誌',
						childtype: [
							{name: '中文書'},
							{name: '外文書'}
						],
					},
					{
						typename: '電子書',
						childtype: [
							{name: '電子書'},
							{name: '電子雜誌'}
						],
					},
					{
						typename: '影音專區',
						childtype: [
							{name: '唱片CD'},
							{name: '影音DVD'}
						],
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

<style lang="sass">
.type-box
	display: flex
	flex-direction: column
	justify-content: center
	align-items: flex-start
	.panel-title
		font-size: 1.25rem
		width: 100%
		text-align: left
		background-color: #f8f8f8
		p
			padding: 1rem 0.5rem

	.panel-child
		font-size: 1rem
		width: 100%
		text-align: left
		border-bottom: solid 1px #eee
		&:last-child
			border-bottom: none
		p
			padding: 0.25rem 1rem
			transition: 0.5s
			&:before
					content: ""
					opacity: 0
					transition: 0.5s
			&:hover
				padding-left: 2rem
				&:before
					content: "▶"
					opacity: 1

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
</style>
