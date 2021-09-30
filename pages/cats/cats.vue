<template>
	<view class="content">
		<!-- 在scroll-view外边再包一个容器，
		它的高度小于scroll-view的高度，达到隐藏了滚动条的效果。 -->
		<view class="scroll-view-box">
			<scroll-view class="box" :scroll-left="offsetLeft" scroll-x="true" scroll-with-animation="true"
				:scroll-into-view="intoindex">
				<view @click="handleClick($event,index)" v-for="(item,index) in content" :key="item.id"
					class="item_title" :class="[currentIndex === index ? 'active':'']">
					{{item.title}}
				</view>
			</scroll-view>
		</view>

		<swiper class="swiper-box" :current="currentTab" @change="currentChange">
			<swiper-item>
				<view class="swiper-item">1</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">2</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">3</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">4</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">5</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">6</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">7</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">8</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">9</view>
			</swiper-item>
			<swiper-item>
				<view class="swiper-item">10</view>
			</swiper-item>

		</swiper>
	</view>
</template>

<script>
	export default {
		data() {
			return {
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
				intoindex: '',
				num: 0, //动态模拟需要跳到的位置
				currentIndex: 0,
				currentTab: 0,
				offsetLeft: 0,

			}
		},
		created() {

		},
		methods: {
			handleClick(evt, index) {
				this.currentIndex = index;
				this.currentTab = index;
				this.offsetLeft = evt.currentTarget.offsetLeft - 150;
			},
			currentChange(e) {
				this.currentIndex = e.detail.current;
				this.intoindex = 'vid' + e.detail.current
			}
		},
		updated() {

		}
	}
</script>

<style>
	.scroll-view-box {
		/* 这个设置就能隐藏滚动条*/
		overflow: hidden;
		height: 60rpx;
	}

	.box {
		white-space: nowrap;
		height: 80rpx;
		margin-bottom: 30rpx;
		text-align: center;
		margin: 10rpx;
	}



	.item_title {
		display: inline-block;
		width: 140rpx;
		text-align: center;
		color: #C0C0C0;
		font-size: 35rpx;
	}

	.swiper-box {}

	.swiper-item {
		color: red;
		font-size: 70rpx;
		text-align: center;
	}

	.active {
		font-size: 40rpx;
		color: #007AFF;
		font-weight: bold;
	}
</style>
