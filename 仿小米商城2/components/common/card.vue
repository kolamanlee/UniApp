<template>
	<view class="card">
		<!-- 写基础卡片组件 -->
		<!-- head -->
		<view v-if="showHead" class=" p-2 border-bottom main-border-color">
			<slot name = "title">
				<text v-if="headTitle" class="font-md font-weight">{{headTitle}}</text>
			</slot>
		</view>
		<!-- body -->
		<view class="">
			<image :src="bodyCover" mode="widthFix"></image>
			
			<slot/>
		</view>
	</view>
	
</template>

<script>
	export default{
		props:{
			headTitle: String,
			bodyCover: String,
			showHead:{
				type: Boolean,
				default: true				
			}				
		}
	}
</script>

<style>
</style>
