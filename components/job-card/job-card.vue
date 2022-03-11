<template>
	<view style="background: #fff;border-radius: 10rpx; padding: 40rpx 30rpx;margin-bottom: 24rpx;">
		<view style="display: flex; justify-content: space-between; font-size: 30rpx;">
			<view style="font-weight: bold;">主任医师</view>
			<view style="color: #b22d33;">30K-60K</view>
		</view>
		<view style="display: flex; margin: 14rpx 0 24rpx 0;">
			<view v-for="i in 3" style="background: #dcdcdc; height:30rpx; border-radius: 5rpx; line-height: 30rpx; text-align: center; min-width: 110rpx; font-size: 20rpx; margin-right: 14rpx;">满5年</view>	
		</view>
		<view style="display: flex; align-items: center; justify-content: space-between; font-size: 20rpx;">
			<view style="display: flex; align-items: center;"><u-avatar src="https://cdn.uviewui.com/uview/album/1.jpg" size="23"></u-avatar><text style="margin-left: 14rpx;">李先生</text></view>
			<view style="color:#afadab; display: flex; align-items: center;"><u-icon name="map-fill" color="#afadab" size="20"></u-icon><text style="margin-left: 6rpx;">长春</text></view>	
		</view>
	</view>
</template>

<script>
	export default {
		name:"job-card",
		data() {
			return {
				
			};
		}
	}
</script>

<style>

</style>
