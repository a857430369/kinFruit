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
				<view class="controls-title">
					<video class="video_index" src="../../static/shouye_1.png" controls></video>
					<cover-view>

						<cover-view class="titleContent">
							<cover-view style="font-weight: 600;font-family: 'Microsoft YaHei';">居然水果商城入住本地</cover-view>
							<cover-view class="activeHot">
								<cover-image style="width: 48rpx; height: 48rpx;" src="../../static/火.png"></cover-image>
								<cover-view style="margin-top: 10rpx;font-size: 25rpx;">活动</cover-view>
							</cover-view>
						</cover-view>
					</cover-view>
					<view class="contentHot">
						<view style="font-size: 25rpx;">
							天天快乐 20分钟前完成领取
						</view>
						<view class="progress-box">
							<progress percent="20" font-size="12" border-radius="10" show-info stroke-width="20" />
						</view>
					</view>

				</view>
				<view class="buttonSet">
					<button class="buttonGet" type="primary">立即领取</button>
				</view>
			</view>
		</view>
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

<style scoped>
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
		height: 325rpx;
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

	.controls-title {
		margin: auto;
		padding: 20rpx;
		margin-top: 20rpx;
		border-radius: 25rpx;
		width: 650rpx;
		background-color: #FFFFFF;
	}

	.video_index {
		width: 100%;
		height: 380rpx;
		border-radius: 25rpx;
	}

	/* 首页活动 */
	.titleContent {
		display: flex;
		margin: 10px 0 0px 0;
	}

	.activeHot {
		background-color: red;
		padding: 2rpx 20rpx 6rpx 10rpx;
		margin-left: 10rpx;
		font-size: 10rpx;
		color: #FFFFFF;
		display: flex;
		border-radius: 25rpx;
	}

	.buttonSet {
		width: 90%;
		margin-top: 4%;
		margin-left: 5%;
	}

	.contentHot {
		font-size: 10rpx;
		margin-top: 10rpx;
		display: flex;
		justify-content: space-between;
	}

	.progress-box {
		margin-left: 2%;
		width: 300rpx;
	}

	.progressSet {
		font-size: 1rpx;
		border-radius: 25px;
	}

	/* 立即领取 */
	.buttonGet {
		width: 100%;
		border-radius: 35rpx;
		bottom: 0;
		background-color: #018A56;
	}
</style>
