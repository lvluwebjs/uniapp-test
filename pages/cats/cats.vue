<template>
	<view class="content">
		<!-- 在scroll-view外边再包一个容器，
		它的高度小于scroll-view的高度，达到隐藏了滚动条的效果。 -->
		<view class="scroll-view-box">
			<scroll-view class="box" :scroll-left="offsetLeft" scroll-x="true" scroll-with-animation="true"
				>
				<view @click="handleClick($event,index)" v-for="(item,index) in content" :key="item.id"
					class="item_title" :class="[currentIndex === index ? 'active':'']">
					{{item.title}}
				</view>
			</scroll-view>
		</view>

		<swiper class="swiper-box" :current="currentTab" @change="currentChange">
			<swiper-item class="swiper-item" v-for="itemNum in numList">
				{{itemNum}}
			</swiper-item>

		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				numList: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10],
				content: [{
					id: 0,
					title: "关注"
				}, {
					id: 1,
					title: "推荐"
				}, {
					id: 2,
					title: "全部"
				}, {
					id: 3,
					title: "完赛"
				}, {
					id: 4,
					title: "专家"
				}, {
					id: 5,
					title: "装备"
				}, {
					id: 6,
					title: "NBA"
				}, {
					id: 7,
					title: "CBA"
				}, {
					id: 8,
					title: "英超"
				}, {
					id: 9,
					title: "西甲"
				}, ],
				moveWidth: 0,
				currentIndex: 0,
				currentTab: 0,
				offsetLeft: 0,

			}
		},
		created() {

		},
		onLoad() {
			uni.getSystemInfo({
				success: (res) => {
					this.moveWidth = res.windowWidth
				}
			})
		},
		methods: {
			handleClick(evt, index) {
				this.currentIndex = index;
				this.currentTab = index;
                this.offsetLeft = (index-2) * this.moveWidth / 5;
				console.log(this.offsetLeft)
			},
			currentChange(e) {
				this.currentIndex = e.detail.current;
                this.offsetLeft = (e.detail.current-2) * this.moveWidth / 5;
			}
		},
		updated() {

		}
	}
</script>

<style>
	html,
	body {
		width: 100%;
		height: 100%;
	}

	.content {
		width: 100%;
		height: 100%;

	}

	.scroll-view-box {
		/* 这个设置就能隐藏滚动条*/
		overflow: hidden;
		height: 60rpx;
	}

	.box {
		height: 80rpx;
		width: 100%;
		box-sizing: border-box;
		overflow: hidden;
		line-height: 80rpx;
		background: #f7f7f7;
		font-size: 16px;
		white-space: nowrap;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 99;
	}



	.item_title {
		width: 20%;
		display: inline-block;
		text-align: center;
	}

	.swiper-box {
		background: greenyellow;
		padding-top: 80rpx;
		height: 100%;
		box-sizing: border-box;
	}

	.swiper-item {
		overflow-y: scroll;
	}

	.active {
		font-size: 40rpx;
		color: #007AFF;
		font-weight: bold;
	}
</style>
