<script>
	export default {
		onLaunch: function() {
			uni.removeStorage({
				key: 'offsetLeft_key',
			});
		},
		onShow: function() {
			console.log('App Show')
		},
		onHide: function() {
			console.log('App Hide')
		},

	}
</script>

<style>
	/*全局页面公共css样式 */
</style>
