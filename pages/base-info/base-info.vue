<template>
	<view class="base-info-wrapper">
		<view style="font-size: 38rpx;color: #5c5c5c;">填写您的基本资料</view>
		<view class="info-input-wrapper" style="margin-top: 90rpx">
			<FormItem title="目前工作地点" :columns="[Locations[0], Locations[1][0]]" :columnData="Locations[1]"></FormItem>
			<FormItem title="期望年薪" :columns="[YearSalary[0], YearSalary[1][0]]" :columnData="YearSalary[1]"></FormItem>
			<FormItem title="职业类别" :columns="JobTypes"></FormItem>
			<FormItem title="职业年限" :columns="WorkYears"></FormItem>
			<FormItem title="工作方式" :type="'select'" :options="['到场','不到场']"></FormItem>
			<FormItem title="目前在职情况" :columns="[['在职','离职']]"></FormItem>
			<FormItem title="联系电话" :type="'input'"></FormItem>
		</view>
		<view style="position:fixed; bottom: 80rpx;left:92rpx; width: 566rpx; margin: 0 auto;">
			<u-button @tap="" text="下一步" shape="circle" type="primary"></u-button>
		</view>
	</view>
</template>

<script> 
	import FormItem from '../../components/form-item/form-item.vue'
	import {
		Locations,
		YearSalary,
		JobTypes,
		WorkYears
	} from '../../common/const'
	export default {
		components: {
			FormItem
		},
		data() {
			return {
				Locations,
				YearSalary,
				JobTypes,
				WorkYear
			};
		},
		methods: {}
	}
</script>

<style lang="scss">
	.base-info-wrapper {
		padding: 160rpx 54rpx 100rpx 54rpx;
	}
</style>
