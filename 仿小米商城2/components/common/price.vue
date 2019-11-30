<template>
	<view class="d-flex main-text-color font-md">
		<text class="a-self-start font-sm">￥</text>{{price}}
	</view>
</template>

<script>
	export default{
		props:{
			price:[Number, String]
		}
	}
</script>

<style>
</style>
