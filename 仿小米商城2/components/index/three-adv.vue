<template>
	<view class="d-flex">
		<image :src="resdata.big.src" lazy-load="true" style="width:373upx; height: 530upx;border-right: 2upx solid #F5F5F5;"
		@tap="event(resdata.big)"></image>
		<view class="d-flex flex-column">
			<image :src="resdata.smalltop.src" style="width: 375upx;height: 264upx;border-bottom: 2upx solid #F5F5F5;"
			@tap="resdata.smalltop"></image>
			<image :src="resdata.smallbottom.src" style="width: 375upx;height: 264upx;"
			@tap="resdata.smallbottom"></image>
		</view>
	</view>

</template>

<script>
	export default{
		props:{
			resdata:Object
		},
		methods:{
			event(item){
				console.log("点击了图片")
			}
		}
	}
</script>

</style>

<style>