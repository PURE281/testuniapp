<template>
	<view>
		<view class="view-introducation">
			<text class="introducation">分类</text>
			<text class="introducation">{{habitList[0].title}}</text>
			<!-- 开始展示数据 -->
		</view>
		<!-- {{habitList}} -->
		<view>
			<scroll-view :scroll-top="scrollTop" scroll-y="true" class="scroll-Y" 
		<!-- @scrolltoupper="upper"<!--rolltolower="lower" @scroll="scroll" -->
				<view class="content" v-for="(item,index) in habitList" :key="index">
					<taskSingleton :habitItem="item"></taskSingleton>
				</view>
			</scroll-view>
		</view>
	</view>


</template>

<script>
	// const urls = ["http://iwenwiki.com/api/FingerUnion/list.php"]
	import taskSingleton from '@/pages/content/tasksingleton.vue'
	
	export default {
		components:{
			taskSingleton
		},
		data() {
			return {
				list: [],
				scrollTop: 0,
				habitItem:{}
			}
		},
		props: ['habitList'],
		mounted() {
			//加载数据
			// console.log(getApp().globalData.apiUrls[0]);
			// uni.request({
			// 	url: getApp().globalData.apiUrls[0],
			// 	success: (res) => {
			// 		this.list = res.data.data;
			// 	},fail: (e) => {
			// 		console.log(e)
			// 	}
			// })
			// LoadData();
		},
		methods: {
			// LoadData() {
			// 	uni.request({
			// 		url: urls[0],
			// 		success: (res) => {
			// 			// console.log(res.data)
			// 		}
			// 	})
			// },
			showDetail(index) {
				console.log(index);
			}
		}
	}
</script>

<style>
	.view-introducation {
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.introducation {
		margin: 1ch;
		color: #fff;
	}

	.content {
		/* margin-top: 0.5ch; */
	}
</style>
