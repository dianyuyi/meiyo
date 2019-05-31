<template lang="pug">
.contain
		.full-row._between.row
				.depart-col-15.about.m-b-l
						h3 關於枚酉<br>
						p 創辦理念
						p 購物流程
						p 加入會員
						p 枚酉徵稿辦法
						p 枚酉徵才資訊
				.depart-col-15.service.m-b-l
						h3 購書服務<br>
						p 訂單查詢服務
						p 物流取貨方式
						p 退換貨服務
						p VIP折扣方案
						p 常見疑難
				.depart-col-40.fb.m-b-l
						h3 即時書訊<br>
						img(src="https://goo.gl/FEsFmQ", alt="")
				.depart-col-30.contact.m-b-l
						h3 聯繫我們<br>
							.box
								i.fa.fa-map-marker.map
							span 公司地址　
							span 台北市枚酉區枚酉路一段123號0樓之1<br>
							.box
								i.fa.fa-mobile.tele
							span 客服專線　
							span (00)00000000<br>
							.box
								i.fa.fa-envelope-o
							span 客服信箱　
							span meiyo@meiyo.com.tw<br>
</template>

<style lang="sass">
.contain
	background-color: #f7f0dc
	color: #5b5b5b
	padding: 0
	margin: 0px
	display: block
	width: 100%
	.row
		margin: 0px auto
		padding: 30px
		background-color: #f7f0dc
		max-width: 1252px
		.about,.service,.fb,.contact
			h3
				font-size: 1.2rem
				text-align: left
				font-weight: 700
				padding-bottom: 10px
			p,span,i,img
				font-size: 1rem
				cursor: pointer
				text-align: left
		.contact
			line-height: 30px
			.box
				padding-top: 10px
				display: inline-block
				width: 20px
				cursor: pointer
				text-align: center
				vertical-align: center
</style>
