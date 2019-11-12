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


### 


### 

### 网上相关资源
```
1. 阿里巴巴图标库：https://www.iconfont.cn/
2. css动画库:  https://daneden.github.io/animate.css/
3. 取色值工具：
4. 
```
### 
### 