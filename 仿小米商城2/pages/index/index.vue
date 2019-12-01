<template>
	<view class="">
		<!-- 顶部选项卡 -->
		<scroll-view scroll-x="true" class=" border scroll-row" style="height: 80rpx;" :scroll-into-view="scrollinto">
			<view class="scroll-row-item px-3" @click="changeTab(index)" style="height: 80rpx; line-height: 80rpx;" v-for="(item,index) in tabBars"
			 :key="index" :class="tabIndex == index? 'main-text-color':''" :id="'tab'+index">
				<text class="font-md">{{item.name}}</text>
			</view>
		</scroll-view>

		<swiper :current="tabIndex" :style="'height:'+scrollH+'rpx;'">
			<swiper-item v-for="(item,index) in newsitems" :key="index">
				<scroll-view scroll-y="true" :style="'height:'+scrollH+'rpx;'">
					<block v-for="(list, listIndex) in item.list" :key="listIndex">

						<!-- 轮播图组件 -->
						<swiper-image v-if="list.type === 'swipers' " :resdata="list.data"></swiper-image>

						<template v-else-if="list.type === 'indexnavs' ">
							<!-- 图标分类组件 -->
							<index-nav :resdata="list.data"></index-nav>
							<!-- 分割线组件:因为很多页面都使用，将其作为全局组件，放在main.js中引入 -->
							<divider></divider>
						</template>

						<template v-else-if="list.type === 'threeAdv' ">
							<!-- 三图广告位组件：左边w:373 h530  右边w375 h263 边h2 -->
							<three-adv :resdata="list.data"></three-adv>
							<divider></divider>
						</template>


						<!-- 卡片组件 -->
						<!-- <card headTitle="每日精选" bodyCover="/static/images/demo/cate_banner.png"></card> -->

						<!-- 列表组件 -->
						<view class="row j-sb" v-else-if="list.type === 'commonList' ">
							<block v-for="(itemCommonList,indexCommonList) in list.data" :key="indexCommonList">
								<common-list :item="itemCommonList" :index="indexCommonList"></common-list>
							</block>
						</view>

					</block>


				</scroll-view>
			</swiper-item>
		</swiper>


		<!-- -->

	</view>
</template>

<script>
	import swiperImage from "@/components/index/swiper-image.vue"
	import indexNav from "@/components/index/index-nav.vue"
	import threeAdv from "@/components/index/three-adv.vue"
	import card from "@/components/common/card.vue"
	import commonList from "@/components/common/common-list.vue"

	// 模拟后端数据
	let demoTabBars = [{
			name: "关注",
		},
		{
			name: "推荐",
		},
		{
			name: "体育",
		},
		{
			name: "热点",
		},
		{
			name: "财经",
		},
		{
			name: "娱乐",
		},
		{
			name: "军事",
		}
	];

	let demo1 = [{
			type: "swipers",
			data: [{
					src: "/static/images/demo/demo4.jpg"
				},
				{
					src: "/static/images/demo/demo4.jpg"
				},
				{
					src: "/static/images/demo/demo4.jpg"
				}
			]
		},
		{
			type: "indexnavs",
			data: [{
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
			]
		},
		{
			type: "threeAdv",
			data: {
				big: {
					src: "/static/images/demo/demo1.jpg"
				},
				smalltop: {
					src: "/static/images/demo/demo2.jpg"
				},
				smallbottom: {
					src: "/static/images/demo/demo3.jpg"
				}
			}
		},
		{
			type: "commonList",
			data: [{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},

			]
		}
	];
	let demo2 = [{
			type: "swipers",
			data: [{
					src: "/static/images/demo/demo4.jpg"
				},
				{
					src: "/static/images/demo/demo4.jpg"
				},
				{
					src: "/static/images/demo/demo4.jpg"
				}
			]
		},
		{
			type: "indexnavs",
			data: [{
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
			]
		},
		{
			type: "threeAdv",
			data: {
				big: {
					src: "/static/images/demo/demo1.jpg"
				},
				smalltop: {
					src: "/static/images/demo/demo2.jpg"
				},
				smallbottom: {
					src: "/static/images/demo/demo3.jpg"
				}
			}
		},
		{
			type: "commonList",
			data: [{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},
				{
					cover: "/static/images/demo/list/1.jpg",
					title: "米家空调",
					desc: "1.5匹变频",
					oprice: 2699,
					pprice: 1366
				},

			]
		}
	];



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
				scrollinto: "tab0",
				tabIndex: 0,
				tabBars: [],
				newsitems: []
			}
		},
		onLoad() {
			// 获取可视区域高度
			uni.getSystemInfo({
				success: (res) => {
					console.log(res)
					// 140upx
					/* #ifdef H5 */
					this.scrollH = 1200
					/* #endif */
					/* #ifndef H5 */
					this.scrollH = res.windowHeight - uni.upx2px(82)
					/* #endif */
				}
			})
			
			// 初如化事件
			this.__init()
		},
		methods: {
			// 初始化事件
			__init(){
				// 获取顶部选项卡
				this.tabBars = demoTabBars
				// 根据顶部选项卡生成页面
				let arr =[]
				for (var i =0; i<this.tabBars.length;i++){
					let obj = {
						list:[]
					}
					// 获取首屏数据
					if(i===0){
						obj.list = demo1
					}					
					arr.push(obj)
				}
				this.newsitems = arr
			},
			
			// 切换选项卡
			changeTab(index) {
				console.log("index:" + index)
				console.log("scrolH:" + this.scrollH)

				if (this.tabIndex === index) {
					return;
				}
				this.tabIndex = index
				this.scrollinto = 'tab' + index
				// 
				addData()
			},
			// 监听滑动列表
			onChangeTab(e) {
				console.log(e.detail.current)
				this.changeTab(e.detail.current)
			},
			// 加载数据
			addData(){
				// 获取当前的数据
				let index = this.tabIndex
				// 请求数据库
				this.newsitems[index].list = demo2
				
			}
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
