<template>

	<view class="all">
		<uni-nav-bar >
			<uni-search-bar  radius="5" placeholder="搜索栏" clearButton="always" cancelButton="always" />
		</uni-nav-bar>

		<view>

		</view>
		<view>

			<image class="bg-img" src="/static/bg.gif"></image>
			<view style="padding-bottom: 10ch;"></view>
			<view>
				<image mode="widthFix" style="width: 30%;" src="../../../static/tabbar1.png" @click="turnto(0)"></image>
			</view>

			<view class="view-img">
				<image mode="widthFix" style="width: 30%;" src="../../../static/tabbar2.png" @click="turnto(1)"></image>
				<image mode="widthFix" style="width: 30%;" src="../../../static/tabbar3.png" @click="turnto(2)"></image>
			</view>
			<view class="view-img">
				<image mode="widthFix" style="width: 30%;" src="../../../static/tabbar4.png" @click="turnto(3)"></image>
				<image mode="widthFix" style="width: 30%;" src="../../../static/tabbar1.png" @click="turnto(4)"></image>
			</view>

			<!-- 星球图标以及对应的点击事件 -->
		</view>

	</view>
</template>

<script>
	import searchbar from '@/uni_modules/uni-search-bar/components/uni-search-bar/uni-search-bar.vue'
	export default {
		components: {
			searchbar
		},
		data() {
			return {
				title: 'Hello',
				city: "123",
				scrollTop: 0,
				windowWidth: 500,
				windowHeight: 500,
			}
		},
		onLoad() {
			uni.getSystemInfo({
				success: (res) => {
					this.windowWidth = res.windowWidth;
					this.windowHeight = res.windowHeight;
				}
			})
			// uni.request({
			// 	url: getApp().globalData.apiUrls.habitList,
			// 	header: {
			// 		"Content-Type": "application/x-www-from-urlencoded"
			// 	},
			// 	timeout: 3000,
			// 	data: {
			// 		"token":"d9d64ead7fd3863c059b22e967c57388",
			// 		"type":1
			// 	},
			// 	//请求类型
			// 	method: 'get',
			// 	success: (res) => {
			// 		console.log(JSON.stringify(res))
			// 	}
			// })
		},
		methods: {
			to() {},
			backto() {
				plus.runtime.quit();
			},
			turnto(index) {
				console.log(index);
				uni.navigateTo({
					url: '/pages/tabbar/classify/classify?index=' + index,
					success() {}
				})

			}

		}
	}
</script>

<style>
	.bg-img {
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		z-index: -1;
		/* mode: widthfix */
	}

	.view-img {
		display: flex;
		flex-direction: row;
		width: 100%;
		/* height: 80rpx; */
		align-items: center; //垂直居中
	}

	image {

		display: block;
		margin: 0 auto;
	}
</style>
