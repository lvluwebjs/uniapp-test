<template>
	<view class="ld">
		<view class="left">
			<view v-for="(item,index) in list" :key="index" :class="{'active':index === currentNum}"
				@tap="setId(index)">
				{{item.title}}
			</view>
		</view>
		<!-- 
			scroll-into-view
			值应为某子元素id（id不能以数字开头）。
			设置哪个方向可滚动，则在哪个方向滚动到该元素
		 -->
		<view class="right">
			<scroll-view scroll-with-animation="true" scroll-y="true" style="white-space: nowrap;height: 200px;"
				:scroll-into-view="clickId" @scroll="scroll" @scrolltolower="scrolltolower">
				<view v-for="(item,index) in list" :key="index" :id="`pos${index}`">
					<view class="title">
						{{item.title}}
					</view>
					<view v-for="(it,idx) in item.list" :key="idx">
						{{it}}
					</view>
				</view>
			</scroll-view>
		</view>
	</view>
</template>
<!-- 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug 有bug -->
<script>
	export default {
		data() {
			return {
				title: 'Hello',
				list: [{
					title: '中餐',
					list: ['盖饭', '扒饭', '咖喱饭', '鸡排饭']
				}, {
					title: '西餐',
					list: ['牛排', '意面', '芝士', '汉堡']
				}, {
					title: '法餐',
					list: ['辣子鸡丁', 'xxx', '肥仔快乐水', '填缝隙']
				}, {
					title: '快餐',
					list: ['薯条', '丸子', '粥', '饮料']
				}],
				clickId: '',
				currentNum: 0,
				topList: []
			}
		},
		onLoad() {

		},
		onReady() {
			this.getNodesInfo()
		},
		methods: {
			setId(index) {
				this.clickId = `pos${index}`
				this.currentNum = index
			},
			scroll(e) {
				console.log(e)
				let scrollTop = e.target.scrollTop
				console.log(this.topList)
				for (let i = 0; i < this.topList.length - 1; i++) {
					let h1 = this.topList[i]
					let h2 = this.topList[1 + i]
					console.log('i = ', i)
					console.log('h1=', h1)
					console.log('scrollTop=', scrollTop)
					console.log('h2=', h2)
					if (scrollTop >= h1 && scrollTop < h2) {
						console.log(1111111)
						this.currentNum = i
						break
					}
				}
			},
			scrolltolower() {
				setTimeout(() => {
					this.currentNum = this.list.length - 1
				}, 80)
			},
			getNodesInfo(e) {
				const query = uni.createSelectorQuery().in(this)
				query.selectAll('.title').boundingClientRect().exec((res) => {
					let nodes = res[0]
					let rel = []
					nodes.map(item => {
						rel.push(item.top)
					})
					this.topList = rel
					console.log(this.topList)
				})
			}
		}
	}
</script>

<style  scoped>
	.ld {
		display: flex;

	}

	.left {
		width: 100px;
		border: 1px solid red;
	}

	.right {
		flex: 1;
		border: 1px solid red;
	}

	.title {
		font-size: 20px;
		font-weight: bold;
		background-color: pink;
	}


	.active {
		background-color: red;
	}
</style>
