<template>
	<u-upload
		:fileList="fileList6"
		@afterRead="afterRead"
		@delete="deletePic"
		name="6"
		multiple
		:maxCount="1"
		width="626rpx"
		height="222rpx"
	>
		<view style="width: 626rpx; height: 222rpx;background: #b5ede9; border-radius: 10rpx;text-align: center;">
			<view style="width: 56rpx;margin: 0 auto; margin-top: 54rpx; margin-bottom: 10rpx;">
				<u-icon name="plus-circle" color="#f7fffc" size="28"></u-icon>
			</view>
			<view style="color:#f7fffc">{{title}}</view>
		</view>
	</u-upload>
</template>

<script>
	export default {
		name:"image-upload",
		props: {
			title: {
				default: '上传',
				type: String
			}
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">

</style>
