<template>
	<view class="content">

		<view class="cart-scroll-view">
			<scroll-view scroll-y class="cart-scroll-view">
				<evan-checkbox-group>
					<label class="cart" v-for="i in 10">
						<view style="padding-top: 50upx;margin-right: 10upx;">
							<evan-checkbox primary-color="#018a56" :value="item" :checked="item" />
						</view>
						<view class="cart-img">
							<image class="cart-img-set" src="../../static/logo.png" mode="widthFix"></image>
						</view>
						<view class="cart-content">
							<view class="cart-content-title">
								这是一个测试商品
							</view>
							<view class="cart-content-remark">
								这是一个测试备注
							</view>
							<view class="cart-content-price">
								<view class="cart-content-price-countprice">
									￥100.00
								</view>
								<view class="cart-content-price-count">
									<uni-number-box></uni-number-box>
								</view>
							</view>
						</view>
					</label>
				</evan-checkbox-group>
			</scroll-view>
		</view>

		<view class="cart-count-price-pay">
			<view class="cart-count-all">
				<evan-checkbox primary-color="#018a56" :value="item" :checked="item" />
				<lable style="margin-left: 10rpx;">全选</lable>
			</view>
			<view class="cart-count-content">
				<label>共2件商品</label>
				<label style="margin-left: 10rpx;color: red;">合计:￥100.00</label>
				 
			</view>
			<view class="cart-count-sure">
				<button class="cart-count-sure-button" type="primary">结算</button>
			</view>
		</view>
	</view>
</template>

<script>
	import uniNumberBox from "@/components/uni-number-box/uni-number-box.vue"

	export default {
		data() {
			return {

			}
		},
		components: {
			uniNumberBox
		},
		methods: {
			test() {
				console.log('测试')
			}
		}
	}
</script>

<style scoped>
	.cart-scroll-view {
		height: 490px;
	}

	.cart-count-price-pay {
		display: flex;
		align-items: center;
		justify-content: space-between;
		font-size: 14px;
		background-color: #fff;
		height: 65px;
	}

	.cart-count-all {
		display: flex;
		margin-left: 10rpx;
	}

	.cart-count-sure {
		margin-right: 10rpx;
		width: 200rpx;
	}

	.cart-count-sure-button {
		width: 100%;
		border-radius: 50rpx;
		background-color: #018A56;
	}

	.cart {
		display: flex;
		width: 680rpx;
		margin: auto;
		margin-top: 20rpx;
		margin-bottom: 20rpx;
		padding: 20rpx;
		border-radius: 25rpx;
		background-color: #FFFFFF;
	}

	.cart-img-set {
		width: 120rpx;
	}

	.cart-content {
		margin-left: 20rpx;
		width: 80%;
	}

	.cart-content-remark {
		font-size: 25rpx;
		color: #72BEB1
	}

	.cart-content-price {
		display: flex;
		justify-content: space-between;
	}

	.cart-content-price-countprice {
		color: red;
		float: left;
	}

	.cart-content-price-count {
		float: right;
	}
</style>
