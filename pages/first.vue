<template>
	<view class="content">
		<image class="logo" mode="widthFix" src="/static/logo.png"></image>
		<!-- 更新组件 force 是否强制更新    tabbar：页面是否有原生tabbar组件-->
		<app-update ref="app_update" :force="true" :tabbar="false"></app-update>
	</view>
</template>

<script>
	import appUpdate from "@/components/yzhua006-update/app-update"; //app更新组件
	export default {
		data() {
			return {}
		},
		components: {
			appUpdate
		},
		mounted() {
			this.$refs.app_update.update(); //调用子组件检查更新方法
		},
		methods:{
		
		}
	}
</script>

<style lang="scss" scoped>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		width: 400rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}
</style>
