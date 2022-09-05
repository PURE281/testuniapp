<template>
	<view>
		<navigationbar></navigationbar>
		<view class="view-taskDetail">
			<text>{{itemData.title}}</text>
			<text>{{itemData.content}}</text>
			<uni-section title="打卡排行榜"></uni-section>
			<image src="../../static/rank.png" mode="aspectFit"></image>
		</view>

		<view class="btn-view-parent">
			<view class="btn-view">
				<button type="default" style="background-color: aqua;">我的成果</button>
				<button type="default" style="background-color: aqua;" @click="toggle('popupfirst')">立即打卡</button>
			</view>
		</view>
		<view>
			<!-- 普通弹窗 -->
			<uni-popup ref="popuptask" background-color="#fff">
				<image src="../../static/frame.png"></image>

				<view class="example-body">

					<button type="default" style="background-color: aqua;" @click="getPho()">上传</button>
					<view v-for="(item,index) in src" :key="index" style="display: flex;">
						<image :src="item" mode="aspectFit"></image>
					</view>
					<button @click="test">预览</button>
					<!-- <image :src="src"></image> -->
				</view>
			</uni-popup>
		</view>
	</view>
</template>

<script>
	import navigationbar from '@/pages/diybar/navigationBar.vue'

	export default {
		components: {
			navigationbar,
		},
		onLoad(data) {
			this.itemData = data.item.replace(/""/g, "");
			this.itemData = JSON.parse(this.itemData);
		},
		data() {
			return {
				itemData: {},
				isshow: false,
				isupdate: false,
				type: 'center',
				filetype: 0,
				src: [],
				base64Src: ''
			}
		},
		methods: {

			switchupdateform() {},
			toggle(type) {
				this.type = type
				if (type == "popupfirst") {
					// open 方法传入参数 等同在 uni-popup 组件上绑定 type属性
					this.$refs.popuptask.open("bottom")
				} else if (type == "popuptwo") {
					this.$refs.popupfiletype.open("bottom")
				}
			},
			test() {
				uni.showLoading({
					title: "加载中..."
				})
				console.log(this.src.length)
				uni.previewImage({
					current: 0,
					urls: this.src,
					success: (res) => {
						console.log("成功了");
						uni.hideLoading();
					},
					fail: (e) => {
						console.log(e);
						uni.showLoading({
							title: "加载失败..."
						})
					}
				});
			},
			getPho() {
				// 1.
				let that = this;
				uni.chooseImage({
					count: 6, // 最多可以选择的图片张数，默认9
					sizeType: ['original'], //original 原图，compressed 压缩图，默认二者都有
					sourceType: ['album', 'camera'], //album 从相册选图，camera 使用相机，默认二者都有。如需直接开相机或直接选相册，请只使用一个选项
					success: function(res) {

						that.src = res.tempFilePaths;
						console.log(that.src);
						console.log(that.src.length)
					}
				})
			},
		}
	}
</script>

<style lang="scss">
	.view-taskDetail {
		display: flex;
		justify-content: center;
		align-items: left;
		flex-direction: column;
		padding: 10px;
	}

	.example-body {
		padding: 10px;
		padding-top: 0;
	}

	.custom-image-box {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
	}

	.text {
		font-size: 14px;
		color: #333;
	}


	.btn-view-parent {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.btn-view {
		position: fixed;
		bottom: 20rpx;
		display: flex;
		flex-direction: row;
		align-items: center;
		justify-content: center;
	}


	button {
		margin: 50rpx;
	}

	image {
		display: block;
		margin: 0 auto;
	}
</style>
