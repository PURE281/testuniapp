<script>
	export default {
		globalData: {
			habitsList: {
				list1: [{
						"id": 1,
						"title": "坚持积累1",
						"content": "我要做到坚持积累1",
						"teacher_name": "周老师"
					},
					{
						"id": 2,
						"title": "坚持积累2",
						"content": "我要做到坚持积累2",
						"teacher_name": "周老师"
					},
					{
						"id": 3,
						"title": "坚持积累3",
						"content": "我要做到坚持积累3",
						"teacher_name": "周老师"
					},
					{
						"id": 4,
						"title": "坚持积累4",
						"content": "我要做到坚持积累4",
						"teacher_name": "周老师"
					},
					{
						"id": 5,
						"title": "坚持积累5",
						"content": "我要做到坚持积累5",
						"teacher_name": "周老师"
					},
					{
						"id": 6,
						"title": "坚持积累6",
						"content": "我要做到坚持积累6",
						"teacher_name": "周老师"
					}
				],
				list2: [{
						"id": 1,
						"title": "克服恐惧1",
						"content": "我要做到克服恐惧1",
						"teacher_name": "周老师"
					},
					{
						"id": 2,
						"title": "克服恐惧2",
						"content": "我要做到克服恐惧2",
						"teacher_name": "周老师"
					},
					{
						"id": 3,
						"title": "克服恐惧3",
						"content": "我要做到克服恐惧3",
						"teacher_name": "周老师"
					},
					{
						"id": 4,
						"title": "克服恐惧4",
						"content": "我要做到克服恐惧4",
						"teacher_name": "周老师"
					},
					{
						"id": 5,
						"title": "克服恐惧5",
						"content": "我要做到克服恐惧5",
						"teacher_name": "周老师"
					}
				],
				list3: [{
						"id": 1,
						"title": "控制情绪1",
						"content": "我要做到控制情绪1",
						"teacher_name": "周老师"
					},
					{
						"id": 2,
						"title": "控制情绪2",
						"content": "我要做到控制情绪2",
						"teacher_name": "周老师"
					},
					{
						"id": 3,
						"title": "控制情绪3",
						"content": "我要做到控制情绪3",
						"teacher_name": "周老师"
					},
					{
						"id": 4,
						"title": "控制情绪4",
						"content": "我要做到控制情绪4",
						"teacher_name": "周老师"
					},
					{
						"id": 5,
						"title": "控制情绪5",
						"content": "我要做到控制情绪5",
						"teacher_name": "周老师"
					}
				],
				list4: [{
						"id": 1,
						"title": "习惯改进1",
						"content": "我要做到习惯改进1",
						"teacher_name": "周老师"
					},
					{
						"id": 2,
						"title": "习惯改进2",
						"content": "我要做到习惯改进2",
						"teacher_name": "周老师"
					},
					{
						"id": 3,
						"title": "习惯改进3",
						"content": "我要做到习惯改进3",
						"teacher_name": "周老师"
					},
					{
						"id": 4,
						"title": "习惯改进4",
						"content": "我要做到习惯改进4",
						"teacher_name": "周老师"
					},
					{
						"id": 5,
						"title": "习惯改进5",
						"content": "我要做到习惯改进5",
						"teacher_name": "周老师"
					}
				],
				list5: [{
						"id": 1,
						"title": "其他1",
						"content": "我要做到xxx1",
						"teacher_name": "周老师"
					},
					{
						"id": 2,
						"title": "其他2",
						"content": "我要做到xxx2",
						"teacher_name": "周老师"
					},
					{
						"id": 3,
						"title": "其他3",
						"content": "我要做到xxx3",
						"teacher_name": "周老师"
					},
					{
						"id": 4,
						"title": "其他4",
						"content": "我要做到xxx4",
						"teacher_name": "周老师"
					},
					{
						"id": 5,
						"title": "其他5",
						"content": "我要做到xxx5",
						"teacher_name": "周老师"
					}
				],
			},
			apiUrls: {
				"habitList": "http://ameng.iqweb.net/api.php/Habit/slst"
			}
		},
		onLaunch: function() {
			console.log('App Launch')

		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	body {
		background-color: "#000";
	}

	.bg-img {
		position: fixed;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		z-index: -1;
	}
</style>
