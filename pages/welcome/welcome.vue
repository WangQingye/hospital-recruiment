<template>
	<view class="logo-wrapper">
		<view class="logo-img">
			<u--image src="/static/imgs/logo.png" width="140rpx" height="180rpx"></u--image>
		</view>
		<view class="button-wrapper" style="text-align: center;">
			<view style="font-size: 100rpx; font-weight: bold;color: 1e264d">Hello</view>
			<view style="color: 1e264d">欢迎使用政燊医招</view>
			<view class="login-btn" style="width: 35;">
				<u-button @tap="login" text="我要应聘" shape="circle" type="warning"></u-button>
			</view>
			<view class="login-btn">
				<u-button @tap="login" text="我要招聘" shape="circle" type="primary"></u-button>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tips: 'dasdasdsa'
			};
		},
		methods: {
			codeChange() {

			},
			getCode() {

			},
			login() {

			}
		}
	}
</script>

<style lang="scss" scpoed>
	.logo-wrapper {
		width: 100%;
		padding-top: 184rpx;
	
	.logo-img {
			width: 140rpx;
			display: block;
			margin: 0 auto;
		}

		.button-wrapper {
			display: block;
			margin: 0 auto;
			width: 344rpx;
			margin-top: 46rpx;

			/deep/ .u-input {
				height: 60rpx;
				background: #f1f4f6;
				margin-top: 30rpx;
			}

			/deep/ .u-button--plain {
				background: #f1f4f6;
			}

			/deep/ .login-btn {
				margin-top: 40rpx;
			}
		}
	}
</style>
