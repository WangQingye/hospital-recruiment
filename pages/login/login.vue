<template>
	<view class="logo-wrapper">
		<view class="logo-img">
			<u--image src="/static/imgs/logo.png" width="140rpx" height="180rpx"></u--image>
		</view>
		<view class="input-wrapper">
			<u-input shape="circle" placeholder="请输入手机号" prefixIcon="account-fill"
				prefixIconStyle="font-size: 22px;color: #9f9fa0"></u-input>
			<u-input shape="circle" placeholder="请输入手机号" prefixIcon="lock-fill"
				prefixIconStyle="font-size: 22px;color: #9f9fa0">
				<template slot="suffix">
					<u-code ref="uCode" @change="codeChange" seconds="20" changeText="X秒重新获取哈哈哈"></u-code>
					<u-button :plain="true" @tap="getCode" :text="tips" shape="circle" type="primary" size="mini">
					</u-button>
				</template>
			</u-input>
			<view class="login-btn">
				<u-button @tap="login" text="登录" shape="circle" type="primary"></u-button>
			</view>
			<view style="margin-top: 36rpx; font-size: 24rpx; text-align: center; color: #9f9fa0;">登录即表示您同意<text style="color: red;">《政燊医招用户协议》</text></view>
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

		.input-wrapper {
			display: block;
			margin: 0 auto;
			width: 570rpx;
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
