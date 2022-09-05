// 页面
<template>
	<view>
		<navigationBar />
		
		<image class="bg-img" src="/static/bg.png"></image>
		<maincontent :habitList="habitList" />
	</view>

</template>

<script>
	import maincontent from '@/pages/content/classify.vue'
	import navigationBar from '@/pages/diybar/navigationBar.vue'
	
	export default {
		components: {
			maincontent,
			navigationBar
		},
		data() {
			return {
				habitList: [123],
			}
		},
		onLoad(proData) {
			// this.habitList = getApp().globalData.habitsList.list1;
			switch (proData.index) {
				case "0":
					this.habitList = getApp().globalData.habitsList.list1;
					break;
				case "1":
					this.habitList = getApp().globalData.habitsList.list2;
					break;
				case "2":
					this.habitList = getApp().globalData.habitsList.list3;
					break;
				case "3":
					this.habitList = getApp().globalData.habitsList.list4;
					break;
				case "4":
					this.habitList = getApp().globalData.habitsList.list5;
					break;
				default:
					this.habitList = "数据错误";
					break;
			}
			// console.log(proData.index)
			// console.log(getApp().globalData.habitsList.list1)
			// console.log(this.habitList)
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				});
			},
			home() {
				uni.redirectTo({
					url: '/pages/index/index'
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
	}
</style>
