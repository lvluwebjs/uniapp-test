<template>
	<view>
		我是子组件接收父组件传过来的值
		{{msg}}
		<button @click="childmsg(ms)">我是子组件</button>
	</view>
</template>

<script>
	export default {
		name: "child",
		data() {
			return {
              childmessage:'我是子组件传递的值'
			};
		},
		props: {
			msg: {
				type: String,
				default: '传值'
			}
		},
		methods:{
			childmsg(ms){
				console.log(123)
				this.$emit("childEvent",this.childmessage)
			}
		}
	}
</script>

<style>

</style>
