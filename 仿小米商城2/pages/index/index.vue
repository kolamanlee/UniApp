<template>
	<view class="">
		<!-- 顶部选项卡 -->
		<scroll-view scroll-x="true"  class=" border scroll-row" style="height: 80rpx;">
			<view class="scroll-row-item px-3" 
			style="height: 80rpx; line-height: 80rpx;"
			v-for="(item,index) in tabBars" :key="index"
			:class="tabIndex == index? 'main-text-color':''">
			<text class="font-md">{{item.name}}</text>
			</view>
		</scroll-view>

		<swiper :current="tabIndex" :style="'height:'+scrollH+'rpx;'" >
			<swiper-item v-for="(item,index) in tabBars" :key="index">
				<scroll-view scroll-y="true" :style="'height:'+scrollH+'rpx;'">
					<view v-for="i in 100" :key="i">{{i}}</view>
				</scroll-view>
			</swiper-item>
		</swiper>
		
		<!-- 轮播图组件 -->
		<!-- <swiper-image :resdata="swipers"></swiper-image> -->
		<!-- 图标分类组件 -->
		<!-- <index-nav :resdata="indexnavs"></index-nav> -->
		<!-- 分割线组件:因为很多页面都使用，将其作为全局组件，放在main.js中引入 -->
		<!-- <divider></divider> -->
		<!-- 三图广告位组件：左边w:373 h530  右边w375 h263 边h2 -->
		<!-- <three-adv :resdata="threeAdv"></three-adv> -->
		<!-- 卡片组件 -->
		<!-- <card headTitle="每日精选" bodyCover="/static/images/demo/cate_banner.png"></card> -->
		<!-- 列表组件 -->
		<!-- <view class="row j-sb"> -->
			<!-- <block v-for="(item,index) in commonList" :key="index"> -->
				<!-- <common-list :item="item" :index="index"></common-list> -->
			<!-- </block> -->
		<!-- </view> -->
		
		<!-- -->

 </view>
</template>

<script>
	import swiperImage from "@/components/index/swiper-image.vue"
	import indexNav from "@/components/index/index-nav.vue"
	import threeAdv from "@/components/index/three-adv.vue"
	import card from "@/components/common/card.vue"
	import commonList from "@/components/common/common-list.vue"

	export default {
		components: {
			swiperImage,
			indexNav,
			threeAdv,
			card,
			commonList
		},
		data() {
			return {
				tabIndex:0,
				tabBars:[
					{
						name:"关注",
					},
					{
						name:"推荐",
					},
					{
						name:"体育",
					},
					{
						name:"热点",
					},
					{
						name:"财经",
					},
					{
						name:"娱乐",
					},
					{
						name:"军事",
					}
				],
				swipers: [{
						src: "/static/images/demo/demo4.jpg"
					},
					{
						src: "/static/images/demo/demo4.jpg"
					},
					{
						src: "/static/images/demo/demo4.jpg"
					}
				],
				indexnavs: [{
						src: "/static/images/indexnav/1.png",
						text: "新品发布"
					},
					{
						src: "/static/images/indexnav/2.gif",
						text: "小米众筹"
					},
					{
						src: "/static/images/indexnav/3.gif",
						text: "以旧换新"
					},
					{
						src: "/static/images/indexnav/4.gif",
						text: "一分换团"
					},
					{
						src: "/static/images/indexnav/5.gif",
						text: "超值特卖"
					},
					{
						src: "/static/images/indexnav/6.gif",
						text: "小米秒杀"
					},
					{
						src: "/static/images/indexnav/7.gif",
						text: "真心想要"
					},
					{
						src: "/static/images/indexnav/8.gif",
						text: "电热热卖"
					},
					{
						src: "/static/images/indexnav/9.gif",
						text: "家电热卖"
					},
					{
						src: "/static/images/indexnav/10.gif",
						text: "米粉卡"
					}
				],
				threeAdv: {
					big: {
						src: "/static/images/demo/demo1.jpg"
					},
					smalltop: {
						src: "/static/images/demo/demo2.jpg"
					},
					smallbottom: {
						src: "/static/images/demo/demo3.jpg"
					}
				},
				commonList:[
					{
						cover:"/static/images/demo/list/1.jpg",
						title:"米家空调",
						desc:"1.5匹变频",
						oprice:2699,
						pprice:1366						
					},
					{
						cover:"/static/images/demo/list/1.jpg",
						title:"米家空调",
						desc:"1.5匹变频",
						oprice:2699,
						pprice:1366						
					},
					{
						cover:"/static/images/demo/list/1.jpg",
						title:"米家空调",
						desc:"1.5匹变频",
						oprice:2699,
						pprice:1366						
					},
					{
						cover:"/static/images/demo/list/1.jpg",
						title:"米家空调",
						desc:"1.5匹变频",
						oprice:2699,
						pprice:1366						
					},
					
				]
				
			}
		},
		onLoad() {
			// 获取可视区域高度
			uni.getSystemInfo({
				success:(res)=>{
					// 140upx
					/* #ifdef H5 */
					this.scrollH = 1200
					/* #endif */
					/* #ifndef H5 */
					this.scrollH = res.windowHeight - uni.upx2px(82)
					/* #endif */					
				}
			})

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
