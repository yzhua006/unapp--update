<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
	
	</view>
</template>
<script >
	export default {
		data() {
			return {
			}
		},
		onLoad() {
		},
		components: {
		},
		mounted() {
		},
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}
	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
</style>
