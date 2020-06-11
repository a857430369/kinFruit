<template>
	<view>
		<uni-segmented-control class="content-SegmentedControl" :current="current" :values="items" @clickItem="onClickItem"
		 style-type="text" active-color="#4cd964"></uni-segmented-control>
		<scroll-view scroll-y class="content">
			<view class="content">
				<view class="vipContent" v-if="current === 0">
					<view class="content-cheep" v-for="i in 10">
						<image class="vipImg" src="../../static/logo.png" mode="widthFix"></image>
						<view class="content-text">
							<view class="content-text-title">
								我是一个测试商品
							</view>
							<view class="content-text-remark">
								我是备注
							</view>
							<view class="content-text-price">
								<view class="content-text-price-cheep">
									<view style="font-size: 30rpx;">
										￥
									</view>
									<view>
										100.00
									</view>
								</view>
								<view class="content-text-price-normal">
									<view>
										￥180.00
									</view>
								</view>
							</view>
							<view class="content-text-tag">
								<uni-tag size="small" circle text="标签"></uni-tag>
							</view>
							<view class="content-text-cart">
								<image class="cartImg" src="../../static/购物车_2.png" mode="widthFix"></image>
							</view>
						</view>
					</view>
				</view>
				<view v-show="current === 1">
					选项卡2的内容
				</view>
				<view v-show="current === 2">
					选项卡3的内容
				</view>
			</view>
		</scroll-view>
	</view>
</template>

<script>
	import uniSegmentedControl from "../../components/uni-segmented-control/uni-segmented-control.vue"
	import uniTag from "@/components/uni-tag/uni-tag.vue"

	export default {
		data() {
			return {
				items: ['选项卡1', '选项卡2', '选项卡3'],
				current: 0
			}
		},
		components: {
			uniSegmentedControl,
			uniTag
		},
		methods: {
			onClickItem(e) {
				if (this.current !== e.currentIndex) {
					this.current = e.currentIndex;
				}
			}
		}
	}
</script>

<style scoped>
	.content {
		height: 519px;
	}

	.vipContent {
		width: 680rpx;
		margin: auto;
		margin-top: 20rpx;
		padding: 20rpx;
		border-radius: 25rpx;
	}

	.vipContent .content-cheep {
		margin: auto;
		margin-top: 20rpx;
		padding: 20rpx;
		display: flex;
		border-radius: 25rpx;
		background-color: #fff;
	}

	.vipImg {
		width: 170rpx;
	}

	.content-text {
		width: 73%;
		margin-left: 3%;
	}

	.content-text-title {
		font-weight: 600;
	}

	.content-text-remark {
		font-size: 14px;
		color: #72BEB1;
	}

	.content-text-price {
		display: flex;
		font-size: 40rpx;
		color: red;
	}

	.content-text-price-cheep {
		display: flex;
	}

	.content-text-price-normal {
		display: flex;
		align-items: center;
		justify-content: center;
		text-decoration:line-through;
		margin-left: 20rpx;
		color: #72BEB1;
		font-size: 30rpx;
	}

	.content-text-tag {
		border: 1px solid #000000;
		width: auto;
		float: left;
		border-radius: 15rpx;
	}

	.content-text-cart {
		float: right;
		width: 50rpx;
		border-radius: 50rpx;
		height: auto;
		padding: 10rpx 0rpx 0rpx 10rpx;
		background-color: #018A56;
	}

	.cartImg {
		width: 40rpx;
	}
</style>
