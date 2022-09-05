// 页面
<template>
	<view>
		<view class="status_bar">
			<!-- 这里是状态栏 -->
		</view>

		<!-- 自定义状态栏 -->
		<view class="status_title">
			<image class="status_left" src="@/static/left-arrow.png" mode="widthFix" @click="back"></image>
			<view class="status_center"></view>
			<!-- <searchbar></searchbar> -->
			<image class="status_right" src="@/static/mainloadlogo.png" mode="widthFix" @click="home"></image>
		</view>

	</view>
</template>

<script>
	import searchbar from '@/uni_modules/uni-search-bar/components/uni-search-bar/uni-search-bar.vue'
	export default {
		components: {
			searchbar
		},
		onLoad() {
			console.log(123);
		},
		data() {
			return {}
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1
				});
			},
			home() {
				uni.switchTab({
					url: "/pages/tabbar/index/index"
				})
			}
		}
	}
</script>

<style>
	/* 自定义状态栏 */
	.status_bar {
		height: var(--status-bar-height);
		width: 100%;
	}

	/* 自定义导航栏 */
	.status_title {
		box-sizing: border-box;
		display: flex;
		justify-content: space-between;
		align-items: center;
		width: 100%;
		height: 44px;
		padding: 0 16px;
		background-color: #FFFFFF;
	}

	.status_left {
		width: 18px !important;
	}

	.status_center {
		font-size: 17px;
		font-weight: 700;
	}

	.status_right {
		width: 22px;
	}
</style>
