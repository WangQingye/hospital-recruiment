<template>
	<view>
		<view v-if="type=='picker'" class="input-wrapper"
			style="border-bottom: 2rpx solid #bdc0bf; padding-bottom: 6rpx; margin-bottom: 54rpx;">
			<view class="input-title" style="margin-bottom: 26rpx;">
				{{title}}
			</view>
			<view class="input" style="display: flex;justify-content: space-between;" @click="showPicker=true">
				<view v-if="valueText">{{valueText}}</view>
				<view v-else style="color: #bdc0bf">{{placeHolder}}</view>
				<u-icon name="arrow-right"></u-icon>
			</view>
			<u-picker :show="showPicker" @cancel="showPicker=false" ref="uPicker" :columns="columns" @confirm="confirm"
				@change="changeHandler"></u-picker>
		</view>
		<view v-else-if="type=='select'"
			style="border-bottom: 2rpx solid #bdc0bf; padding-bottom: 6rpx; margin-bottom: 54rpx; display: flex;justify-content: space-between">
			<view style="margin-bottom: 26rpx;line-height: 58rpx;">
				{{title}}
			</view>
			<view style="display: flex;justify-content: space-between;">
				<view class="picked"
					style="margin-right: 20rpx; width: 174rpx; height: 58rpx; border-radius: 10rpx;text-align: center;line-height: 58rpx;">
					{{options[0]}}</view>
				<view class="unpicked"
					style="width: 174rpx; height: 58rpx; border-radius: 10rpx;text-align: center;line-height: 58rpx">
					{{options[1]}}</view>
			</view>
		</view>
		<view v-if="type=='input'" class="input-wrapper"
			style="border-bottom: 2rpx solid #bdc0bf; padding-bottom: 6rpx; margin-bottom: 54rpx;">
			<view class="input-title" style="margin-bottom: 26rpx;">
				{{title}}
			</view>
			<view class="input" style="display: flex;justify-content: space-between;">
			  <u--input
				placeholder="请填写" 
				border="none"
				v-model="value"
				@change="change"
			  ></u--input>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		name: "form-item",
		props: {
			title: {
				default: "",
				type: String
			},
			placeHolder: {
				default: '请选择',
				type: String
			},
			columns: {
				default: [
					['中国', '美国'],
					['深圳', '厦门', '上海', '拉萨']
				],
				type: Array
			},
			columnData: {
				default: [],
				type: Array
			},
			options: {
				default: [],
				type: Array
			},
			type: {
				default: 'picker',
				type: String
			}
		},
		data() {
			return {
				showPicker: false,
				valueText: ""
			};
		},
		methods: {
			changeHandler(e) {
				if (this.columns.length === 1) return
				const {
					columnIndex,
					value,
					values, // values为当前变化列的数组内容
					index,
					// 微信小程序无法将picker实例传出来，只能通过ref操作
					picker = this.$refs.uPicker
				} = e
				// 当第一列值发生变化时，变化第二列(后一列)对应的选项
				if (columnIndex === 0) {
					// picker为选择器this实例，变化第二列对应的选项
					picker.setColumnValues(1, this.columnData[index])
				}
			},
			// 回调参数为包含columnIndex、value、values
			confirm(e) {
				console.log('confirm', e)
				this.showPicker = false
				this.valueText = e.value.join('-')
			}
		}
	}
</script>

<style lang="scss">
	.unpicked {
		border: 1px solid #5b5b5b;
		color: #5b5b5b;
	}

	.picked {
		border: 1px solid #47cfc6;
		color: #47cfc6;
	}
</style>
