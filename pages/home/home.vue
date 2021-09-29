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
		<scroll-view scroll-x="true" class="contianer">
			
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
						mode=""></image>
					<view class="">
						京东超市
					</view>
				</view>
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/178015/31/13828/6862/60ec0c04Ee2fd63ac/ccf74d805a059a44.png!q70.jpg.dpg"
						mode="widthFix"></image>
					<view class="">
						数码电器
					</view>
				</view>
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/41867/2/15966/7116/60ec0e0dE9f50d596/758babcb4f911bf4.png!q70.jpg.dpg"
						mode="widthFix"></image>
					<view class="">
						京东服饰
					</view>
				</view>
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/177902/16/13776/5658/60ec0e71E801087f2/a0d5a68bf1461e6d.png!q70.jpg.dpg"
						mode="widthFix"></image>
					<view class="">
						京东生鲜
					</view>
				</view>
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/196472/7/12807/7127/60ec0ea3Efe11835b/37c65625d94cae75.png!q70.jpg.dpg"
						mode="widthFix"></image>
					<view class="">
						京东到家
					</view>
				</view>
				<view class='box'>
					<image
						src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/191060/24/12861/6818/60ec11f2E67cf5ee6/c264378678b3cd96.png!q70.jpg.dpg"
						mode="widthFix"></image>
					<view class="">
						京东国际
					</view>
				</view>
				
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/175540/24/19329/6842/60ec0b0aEf35f7384/ec560dbf9b82b90b.png!q70.jpg.dpg"
					mode=""></image>
				<view class="">
					京东超市
				</view>
			</view>
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/178015/31/13828/6862/60ec0c04Ee2fd63ac/ccf74d805a059a44.png!q70.jpg.dpg"
					mode="widthFix"></image>
				<view class="">
					数码电器
				</view>
			</view>
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/41867/2/15966/7116/60ec0e0dE9f50d596/758babcb4f911bf4.png!q70.jpg.dpg"
					mode="widthFix"></image>
				<view class="">
					京东服饰
				</view>
			</view>
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/177902/16/13776/5658/60ec0e71E801087f2/a0d5a68bf1461e6d.png!q70.jpg.dpg"
					mode="widthFix"></image>
				<view class="">
					京东生鲜
				</view>
			</view>
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/196472/7/12807/7127/60ec0ea3Efe11835b/37c65625d94cae75.png!q70.jpg.dpg"
					mode="widthFix"></image>
				<view class="">
					京东到家
				</view>
			</view>
			<view class='box'>
				<image
					src="https://m.360buyimg.com/mobilecms/s120x120_jfs/t1/191060/24/12861/6818/60ec11f2E67cf5ee6/c264378678b3cd96.png!q70.jpg.dpg"
					mode="widthFix"></image>
				<view class="">
					京东国际
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import Child from '../../components/child.vue'
	export default {
		data() {
			return {
				msg: '',
				listArr: []
			}
		},
		components: {
			Child
		},
		methods: {
			btn() {
				this.listArr.push(this.msg)
				// this.msg = ''
			},
			childEvent(e) {
				console.log(e)
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

	.contianer{
		white-space:nowrap
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
