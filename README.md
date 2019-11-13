### App.vue 引入全局公共样式

引入样式库，放到一个统一目录，如common下
```
uni.css  //官方ui库(uni-app的hello-uni-app中有最新的uni.css,可能需要将/static/uni.ttf也要复制到项目中)
animate.css //css动画库 [animate](https://daneden.github.io/animate.css/)
icon.css //图标库，先创建空的css文件
common.css //公共样式 ，先创建空的css文件
```
设置全局样式
```
1. 页面高度100%, 默认字体28upx, 默认行高1.8
page{
	height: 100%;
	font-size: 28upx;
	line-height: 1.8;
	background: #FFFFFF;
}

2. 图片默认100%宽度
image{ width: 100%;}

3. 设置主色调

/* 主背景颜色（橙色） */	
.main-bg-color{background: #FD6801;}
/* 主点击背景颜色 */
.main-bg-hover-color{background: rgba(253,104,1,0.85);}
/* 主字体颜色（橙色） */
.main-text-color{color: #FD6801;}
/* 主边框颜色 */
.main-border-color{ border-color: #F1F1F1;}

```
### pages.json 全局及底部导航配置

全局配置
```
	"globalStyle": {
		"navigationBarTextStyle": "black",
		"navigationBarTitleText": "仿小米商城",
		"navigationBarBackgroundColor": "#FFFFFF",
		"backgroundColor": "#FFFFFF"
	},

```
底部导航配置
```
	"tabBar":{
		"color":"#B1B1B1",
		"selectedColor":"#Fd6801",
		"borderStyle":"black",
		"backgroundColor":"#FFFFFF",
		"list":[
			{
				"pagePath":"pages/index/index",
				"text":"首页",
				"iconPath":"static/tabbar/index.png",
				"selectedIconPath":"static/tabbar/indexSelected.png"				
			},
			{
				"pagePath":"pages/class/class",
				"text":"分类",
				"iconPath":"static/tabbar/class.png",
				"selectedIconPath":"static/tabbar/classSelected.png"				
			},
			{
				"pagePath":"pages/cart/cart",
				"text":"购物车",
				"iconPath":"static/tabbar/cart.png",
				"selectedIconPath":"static/tabbar/cartSelected.png"
			},
			{
				"pagePath":"pages/my/my",
				"text":"我的",
				"iconPath":"static/tabbar/my.png",
				"selectedIconPath":"static/tabbar/mySelected.png"
			}
		]
		
	}

```


### UI 基础库封装(/common/zcm-main.css)
1. 什么是基础封装库(参考boostrap的css, )
```
颜色：背景颜色/边框颜色/文本颜色
布局：
边框：
内边距：
外边距：
字体大小：
行高：
FLEX布局：
```
example: 在index.vue中使用zcm-main.css,加入如下代码到<template>中: (有问题???)
```
	<view class="d-flex bg-white border-top position-fixed bottom-0 left-0 right-0 " style="height: 90upx;">
		<view class="flex-1 d-flex j-center a-center flex-column line-h">
			<view class="iconfont icon-xihuan line-h"></view>
			收藏			
		</view>
		<view class="flex-1 d-flex j-center a-center flex-column line-h">
			<view class="iconfont icon-gouwuche line-h"></view>
			购物车
		</view>
		<view style="flex:2.5;" class="text-white main-bg-color d-flex j-center a-center flex-column line-h" hover-class="main-bg-hover-color">加入购物车</view>
	</view>

```
2. upx:是在uni-app中定义的屏幕的宽度为750upx.等同于微信中的rpx. 因此所有的宽度和长度都要以前为基础进行计算.
3. 
### 


### 

### 网上相关资源
```
1. 阿里巴巴图标库：https://www.iconfont.cn/
2. css动画库:  https://daneden.github.io/animate.css/
3. 取色值工具：
4. 前框开发框架 bootstrap中文网：https://www.bootcss.com/,https://v4.bootcss.com/docs/4.3/utilities/flex/
utilities/colors
5. photoshop:

```
### 
### 