<template>
	<!-- //这是任务单例 -->
	<view>
		<view class="all" @click="showDetail(habitItem)">
			<image mode="widthFix" class="taskbg" src="@/static/frame.png">

			<view class="view-text">
				<text class="title">标题: {{habitItem.title}}</text>
				<text class="teacher">发布人: {{habitItem.teacher_name}}</text>
				<text class="content">任务内容: {{habitItem.content}}</text>
			</view>
			<!-- <text>这是任务单例</text> -->
		</view>
	</view>


</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {

			showDetail(item) {
				//跳转到任务详情页面
				uni.navigateTo({
					url:'/pages/content/taskDetail?item='+JSON.stringify(item),
					success() {
						console.log("suc")
					},fail: (e) => {
						console.log(e)
					}
				})
			}
		},
		mounted() {},
		props: ['habitItem']

	}
</script>

<style>
	.all {
		position: relative;
		flex-direction: column;
		display: flex;
		justify-content: center;
		align-items: center;
		top: 50upx;
		margin-top: 100upx;
		margin-bottom: 250upx;
	}

	.taskbg {
		z-index: -1;
		position: absolute;
		width: 100%;
		/* left: 0; */
	}

	.view-text {
		color: #fff;
		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	image {
		/* 
		display: block;
		margin: 0 auto; */
	}
</style>
