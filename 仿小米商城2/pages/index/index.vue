<template>
	<view class="">
		<!-- 轮播图组件 -->
		<swiper-image :resdata="swipers"></swiper-image>
		<!-- 图标分类组件 -->
		<index-nav    :resdata="indexnavs"></index-nav>
		<!-- 分割线组件:因为很多页面都使用，将其作为全局组件，放在main.js中引入 -->
		<divider></divider>
		<!-- 三图广告位组件：左边w:373 h530  右边w375 h263 边h2 -->
		<view class="d-flex">
			<image src="/static/images/demo/demo1.jpg"
			lazy-load="true"
			style="width:373upx; height: 530upx;border-right: 2upx solid #F5F5F5;"
			></image>
			
			<view class="d-flex flex-column">
				<image src="/static/images/demo/demo2.jpg"
				style="width: 375upx;height: 264upx;border-bottom: 2upx solid #F5F5F5;"></image>

				<image src="/static/images/demo/demo2.jpg"
				style="width: 375upx;height: 264upx;"></image>
			</view>			
		</view>
		<!--  -->
				
	</view>
</template>

<script>
	import swiperImage from "@/components/index/swiper-image.vue"
	import indexNav from "@/components/index/index-nav.vue"
	export default {
		components:{
			swiperImage,
			indexNav
		},
		data() {
			return {
				swipers:[					
					{src:"/static/images/demo/demo4.jpg"},
					{src:"/static/images/demo/demo4.jpg"},
					{src:"/static/images/demo/demo4.jpg"}
				],
				indexnavs:[
					{src:"/static/images/indexnav/1.png", text:"新品发布"},
					{src:"/static/images/indexnav/2.gif", text:"小米众筹"},
					{src:"/static/images/indexnav/3.gif", text:"以旧换新"},
					{src:"/static/images/indexnav/4.gif", text:"一分换团"},
					{src:"/static/images/indexnav/5.gif", text:"超值特卖"},
					{src:"/static/images/indexnav/6.gif", text:"小米秒杀"},
					{src:"/static/images/indexnav/7.gif", text:"真心想要"},
					{src:"/static/images/indexnav/8.gif", text:"电热热卖"},
					{src:"/static/images/indexnav/9.gif", text:"家电热卖"},
					{src:"/static/images/indexnav/10.gif", text:"米粉卡"}
				]
			}
		},
		onLoad() {

		},
		methods: {

		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
