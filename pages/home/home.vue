<template>
	<view style="background: #f8f8f8; min-height:100vh;">
		<view class="search-wrapper">
			<view>
				<view style="width:438rpx">
					<u-search color="#5b5d5e" bgColor="#a2e8e3" placeholder="搜索职位" v-model="keyword" :show-action="false"></u-search>
				</view>
			</view>
		</view>
		<view class="home-img" style="margin: 0 auto; width: 680rpx; margin-top: -250rpx">
			<u--image radius="10rpx" src="/static/imgs/home-img.jpg" width="680rpx" height="286rpx"></u--image>
		</view>
		<view class="job-type" style="display: flex; padding: 0 36rpx; margin-top:50rpx; justify-content: space-between; align-items: center;">
			<view style="display: flex;" @click="showJobType = true">
				<text style="font-size: 30rpx;color: #47CFC6;margin-right: 10rpx; font-weight: bold;">职位分类</text>
				<u-icon name="arrow-down-fill" color="#47CFC6" size="12"></u-icon>
				<u-picker :show="showJobType" @cancel="showJobType=false" ref="uPicker" :columns="JobTypes"></u-picker>
			</view>
			<view style="width:476rpx; heght: 76rpx; border-radius: 38rpx; overflow: hidden;">
				<u-notice-bar :icon="' '" bgColor="#fff" fontSize="12" duration="4000" color="#47CFC6" direction="column" :text="text1"></u-notice-bar>
			</view>
		</view>
		<view class="job-list" style="padding: 0 36rpx; margin-top: 36rpx;">
			<JobCard></JobCard>
			<JobCard></JobCard>
			<JobCard></JobCard>
			<JobCard></JobCard>
		</view>
	</view>
</template>

<script>
	import JobCard from '../../components/job-card/job-card.vue'
	import {
		JobTypes
	} from '../../common/const'
	export default {
		components: {
			JobCard
		},
		data() {
			return {
				keyword: '',
				JobTypes,
				text1: ['某某医师成功就职机构年薪50000元', '某某医师成功就职机构年薪100000元'],
				showJobType: false
			};
		}
	}
</script>

<style lang="scss">
	.search-wrapper {
		padding: 0 36rpx;
		padding-top: 96rpx;
		height: 390rpx;
		background: #47CFC6;
	}
</style>
