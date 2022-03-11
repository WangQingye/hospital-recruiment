<template>
	<view class="upload-certificate-wrapper">
		<view style="font-size: 38rpx;color: #5c5c5c;">上传您的资质图片</view>
		<view class="info-input-wrapper" style="margin-top: 90rpx">
			<view style="margin-bottom: 36rpx">
				<ImageUpload :title="'上传职业证'"></ImageUpload>
			</view>
			<view style="margin-bottom: 36rpx">
				<ImageUpload :title="'上传资格证'"></ImageUpload>
			</view>
			<view style="margin-bottom: 36rpx">
				<ImageUpload :title="'上传职称证'"></ImageUpload>
			</view>
			<view style="color:#5c5c5c; font-size:22rpx;margin: 80rpx 0 20rpx 0;">本平台根据国家法律规定严格保护您的信息隐私。</view>
			<view style="color:#5c5c5c; font-size:22rpx">您所上传证件展示我们将对您的信息进行遮挡处理。</view>
		</view>
		<view style="position:fixed; bottom: 80rpx;left:92rpx; width: 566rpx; margin: 0 auto;">
			<u-button @tap="" text="完成上传" shape="circle" type="primary"></u-button>
		</view>
	</view>
</template>

<script>
	import ImageUpload from '../../components/image-upload/image-upload.vue'
	export default {
		components: {
			ImageUpload
		},
		data() {
			return {
			};
		},
		methods: {}
	}
</script>

<style lang="scss">
.upload-certificate-wrapper {
	padding: 160rpx 54rpx 100rpx 54rpx;
}
</style>
