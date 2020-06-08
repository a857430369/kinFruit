<template>
	<view class="content">
		<view class="index_header">
			<view class="local_scan">
				<view class="icon_local">
					<image class="icon_local_image" src="../../static/local.png"></image>
				</view>
				<view class="local_text">
					<text>郭洲村</text>
				</view>
				<view class="icon_scan">
					<image class="icon_scan_image" src="../../static/scan.png"></image>
				</view>
			</view>
			<view class="icon_function">
				<view class="icon_function_item">
					<view class="icon_demo">
						<image class="icon_demo_image" src="../../static/gift.png"></image>
					</view>
					<view class="icon_text">
						<text>新店开业</text>
					</view>
					<view class="icon_fuzhu_text">
						<text>领取更多好礼</text>
					</view>
				</view>
				<view class="icon_function_item">
					<view class="icon_demo">
						<image class="icon_demo_image" src="../../static/choujian.png"></image>
					</view>
					<view class="icon_text">
						<text>抽奖</text>
					</view>
					<view class="icon_fuzhu_text">
						<text>0</text>
					</view>
				</view>
				<view class="icon_function_item">
					<view class="icon_demo">
						<image class="icon_demo_image" src="../../static/wallet.png"></image>
					</view>
					<view class="icon_text">
						<text>现金·金额</text>
					</view>
					<view class="icon_fuzhu_text">
						<text>0</text>
					</view>
				</view>
			</view>
			<view>
				<cover-image class="controls-pause img" src="../../static/shouye_1.png"></cover-image>
				<cover-view class="controls-title">
					<!-- <view class="index_video"> -->
						<video class="video_index" src="../../static/shouye_1.png" controls></video>
					<!-- </view> -->
					
					<view>123131321</view>
				</cover-view>
			</view>
		</view>
		<!-- <view>
			<view class="goods" v-for="(item, index) in 3" :key="index">
				<image class="goods_image" src="../../static/logo.png"></image>
			</view>

	</view> -->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				scrollTop: 0,
				old: {
					scrollTop: 0
				}
			}
		},
		methods: {
			upper: function(e) {},
			lower: function(e) {},
			scroll: function(e) {
				this.old.scrollTop = e.detail.scrollTop
			},
			goTop: function(e) {
				this.scrollTop = this.old.scrollTop
				this.$nextTick(function() {
					this.scrollTop = 0
				});
				uni.showToast({
					icon: "none",
					title: "纵向滚动 scrollTop 值已被修改为 0"
				})
			}
		}
	}
</script>

<style>

	.local_scan {
		display: flex;
		width: 100%;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.goods {
		width: 48%;
		margin: 5rpx;
		float: left;
		box-sizing: border-box;
		padding-bottom: 10rpx;
		position: relative;
	}

	.goods_image {
		width: 100%;
	}

	.index_header {
		background-color: #018A56;
		height: 345rpx;
		width: 750rpx;
	}

	.icon_local {
		height: 50rpx;
		width: 50rpx;
	}

	.icon_local_image {
		height: 100%;
		width: 100%;
	}

	.icon_scan {
		margin-left: auto;
		margin-right: 30rpx;
		height: 50rpx;
		width: 50rpx;
	}

	.icon_scan_image {
		height: 100%;
		width: 100%;
	}

	.icon_function {
		display: flex;
		margin-top: 30rpx;
		justify-content: center;
	}

	.icon_function_item {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		margin: 30rpx;
		margin-top: 0rpx;
		height: 100%;
		width: 100%;
	}

	.icon_demo {
		height: 80rpx;
		width: 80rpx;
	}

	.icon_demo_image {
		height: 100%;
		width: 100%;
	}

	.local_text {
		color: #FFFFFF;
	}

	.icon_text {
		width: 100%;
		text-align: center;
		color: #FFFFFF;
	}

	.icon_fuzhu_text {
		font-size: 25rpx;
		color: #FFFFFF;
	}

	.controls-pause {
		border-radius: 25rpx;
		width: 650rpx;
		height: 125rpx;
		margin: auto;
		right: 50rpx;
	}
	.controls-title{
		margin: auto;
		padding: 20rpx;
		margin-top: 20rpx;
		border-radius: 25rpx;
		width: 650rpx;
		background-color: #FFFFFF;
	}
	.index_video{
		/* width: 100%; */
	}
	.video_index{
		width: 100%;
		border-radius: 25rpx;
	}
</style>
