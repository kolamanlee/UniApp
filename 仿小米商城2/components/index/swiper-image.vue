<template>
	<view >
		<swiper :indicator-dots="true" :autoplay="true" :interval="3000" :duration="1000" :circular="true">
			<block v-for="(item,index) in resdata" :key="index">
				<swiper-item>
					<view class="swiper-item" @tap="event(item)">
						<image :src="item.src" 
						lazy-load style="height: 350upx;" mode="">
						</image>
					</view>
				</swiper-item>
		
			</block>
		</swiper>
		
	</view>
</template>

<script>
	export default{
		props:{
			resdata:Array
		},
		methods:{
			event(item){
				console.log("点击了轮播图片")
			}
		}
	}
</script>

<style>
</style>
