<template>
	<view class="home">
		<!-- <input type="text" v-model="msg" />
		<button @click="btn">输入</button>
		<view class="box">
			<view class="list" v-for="item in listArr" :key='index'>
				{{item}}
			</view>
		</view>
		<Child :msg="msg" @childEvent="childEvent"></Child> -->
		<!-- <scroll-view scroll-x="true" @scrolltoupper="lefttop" class="contianer" @scrolltolower="rightbottom"
			@scroll="scrollview" scroll-with-animation="true" scroll-into-view="{{intoView}}">

			<view class='box' v-for="(item,index) in listArr" @click="scrollturn(index)" :key="index">
				<image :src="item.imgurl" mode="widthFix"></image>
				<view class="">
					{{item.title}}
				</view>
			</view>

		</scroll-view> -->
	</view>
</template>

<script>
	import Child from '../../components/child.vue'
	export default {
		data() {
			return {
				msg: '',
				listArr: [{
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}, {
					title: "京东超市",
					imgurl: "https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
				}],
				intoView: '',
				ids: null
			}
		},
		components: {
			Child
		},
		methods: {
			// btn() {
			// 	this.listArr.push(this.msg)
			// 	// this.msg = ''
			// },
			childEvent(e) {
				console.log(e)
			},
			rightbottom() {
				// console.log('滚动到底部/右边，会触发 scrolltolower 事件')
			},
			lefttop() {
				// console.log('滚动到顶部/左边，会触发 scrolltoupper 事件')
			},
			scrollview() {

				// console.log('滚动时触发，event.detail = {scrollLeft, scrollTop, scrollHeight, scrollWidth, deltaX, deltaY}')
			},
			scrollturn(index) {
				this.intoView = "id" + index;
				console.log(this.intoView)
				
			}
		}
	}
</script>

<style>
	.home {

		box-sizing: border-box;
		/* width: 750rpx; */
		padding: 20rpx 20rpx;
	}

	/* .home input {
		width: 700rpx;
		height: 70rpx;
		border: 1px solid black;
		line-height: 70rpx;
		border-radius: 10rpx;
	} */

	.contianer {
		white-space: nowrap
	}

	.box {
		display: inline-block;
		width: 145rpx;
		text-align: center;
	}

	.box image {
		width: 80rpx;
		height: 80rpx;
	}

	.box view {
		font-size: 26rpx;
		color: #808080;
	}
</style>
