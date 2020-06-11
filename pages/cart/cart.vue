<template>
	<view class="content">
		<view class="cart-scroll-view">
			<scroll-view scroll-y class="cart-scroll-view">
				<checkbox-group>
					<label class="cart" v-for="i in 10">
						<view>
							<checkbox :value="item.value" :checked="item.checked" />
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
				</checkbox-group>
			</scroll-view>
		</view>

		<view class="cart-count-price-pay">
			这是付款的地方
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

		}
	}
</script>

<style scoped>
	.cart-scroll-view {
		height: 519px;
	}

	.cart-count-price-pay {
		background-color: #fff;
		height: 36px;
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
