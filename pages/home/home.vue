<template>
	<view class="container">
		<swiper class="banner-swiper" 
				circular 
				autoplay 
				:interval="3000" 
				:duration="800"
				:indicator-dots="true"
				indicator-active-color="#12c2e9">
			<swiper-item class="banner-swiper-item" v-for="(item, index) in swipers" :key="index">
				<image :src="item" mode="aspectFill" class="swiper-image"></image>
			</swiper-item>
		</swiper>
		<view class="content">
			<!-- section-1 begin -->
			<view class="section-1">
				<view class="grid-container">
					<navigator class="grid-item" open-type="switchTab" url="/pages/index/index" hover-class="none">
						<view class="icon-wrapper">
							<image src="/static/images/home/home_icon_ziqu1.png" mode="aspectFit"></image>
						</view>
						<view class="grid-text">
							<text class="title">到店取</text>
							<text class="subtitle">提前下单面排队</text>
						</view>
					</navigator>
					
					<navigator class="grid-item" open-type="navigate" url="/pages/addresses/addresses" hover-class="none">
						<view class="icon-wrapper">
							<image src="/static/images/home/home_icon_waimai1.png" mode="aspectFit"></image>
						</view>
						<view class="grid-text">
							<text class="title">喜外送</text>
							<text class="subtitle">随时喜送到家</text>
						</view>
					</navigator>
				</view>
			</view>
			<!-- section-2 end -->
			<!-- section-2 begin -->
			<view class="section-2">
				<view class="card" @click="navigateToMart">
					<view class="card-content">
						<view class="card-title">
							<image src="/static/images/home/home_icon_baihuo1.png" mode="aspectFit"></image>
							<text>喜茶百货</text>
						</view>
						<text class="card-desc">精选好物 为你而选</text>
					</view>
					<view class="card-bg bg-1"></view>
				</view>
				
				<view class="card" @click="navigateToGroupDinner">
					<view class="card-content">
						<view class="card-title">
							<image src="/static/images/home/home_icon_qiye1.png" mode="aspectFit"></image>
							<text>企业团餐</text>
						</view>
						<text class="card-desc">企业专享优惠</text>
					</view>
					<view class="card-bg bg-2"></view>
				</view>
			</view>
			<!-- section-2 end -->
			<view class="section-3">
				<view class="points-card">
					<view class="points-info">
						<text class="points-label">我的积分</text>
						<text class="points-value">63</text>
					</view>
					<text class="points-desc">可兑换多款精美礼品</text>
					<view class="points-btn">立即使用</view>
				</view>
				
				<view class="qr-card">
					<image src="/static/images/home/home_icon_erweima.png" mode="aspectFit"></image>
					<text>会员码</text>
				</view>
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				swipers: [
					"https://go.cdn.heytea.com/storage/ad/2020/05/21/bfd57914d80d4671b19f5d0ccc176cd5.jpg",
					"https://go.cdn.heytea.com/storage/ad/2020/05/24/49f9b50738dd47878cf1ab54c2eee2e0.jpg",
					"https://go.cdn.heytea.com/storage/ad/2020/05/01/e1c6915022c849fd9492377021aef454.jpg",
					"https://go.cdn.heytea.com/storage/ad/2020/04/27/db60b797c1cd4afabe9666e7df958ffd.jpg",
					"https://go.cdn.heytea.com/storage/ad/2020/05/21/4ba53dda599345bdaf28a08420dd1b6f.jpg"
				]
			}
		},
		methods: {
			navigateToMart() {
				uni.switchTab({
					url: '/pages/mart/mart'
				})
			},
			navigateToGroupDinner() {
				uni.navigateTo({
					url: '/pages/home/group-dinner'
				})
			}
		}
	}
</script>

<style lang="scss" scoped>
	page {
		max-height: 100%;
	}
	
	.banner-swiper {
		width: 100%;
		height: 420rpx;
		
		.swiper-image {
			width: 100%;
			height: 100%;
			border-bottom-left-radius: 30rpx;
			border-bottom-right-radius: 30rpx;
		}
	}
	
	.content {
		margin-top: 40rpx;
		padding: 20rpx;
	}
	
	.section-1 {
		margin-top: -40rpx;
		padding: 20rpx;
		background: #fff;
		border-radius: 20rpx;
		box-shadow: 0 4rpx 20rpx rgba(0, 0, 0, 0.08);
		
		.grid-container {
			display: grid;
			grid-template-columns: repeat(2, 1fr);
			gap: 20rpx;
		}
		
		.grid-item {
			display: flex;
			align-items: center;
			padding: 20rpx;
			background: linear-gradient(135deg, #f6f8fb 0%, #f0f2f5 100%);
			border-radius: 16rpx;
			
			.icon-wrapper {
				width: 80rpx;
				height: 80rpx;
				margin-right: 20rpx;
				
				image {
					width: 100%;
					height: 100%;
				}
			}
			
			.grid-text {
				display: flex;
				flex-direction: column;
				
				.title {
					font-size: 32rpx;
					font-weight: 600;
					color: #333;
				}
				
				.subtitle {
					font-size: 24rpx;
					color: #666;
					margin-top: 4rpx;
				}
			}
		}
	}
	
	.section-2 {
		margin-top: 30rpx;
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		gap: 20rpx;
		
		.card {
			position: relative;
			height: 180rpx;
			border-radius: 20rpx;
			overflow: hidden;
			
			.card-content {
				position: relative;
				z-index: 2;
				padding: 20rpx;
				height: 100%;
				display: flex;
				flex-direction: column;
				justify-content: center;
			}
			
			.card-title {
				display: flex;
				align-items: center;
				margin-bottom: 10rpx;
				
				image {
					width: 40rpx;
					height: 40rpx;
					margin-right: 10rpx;
				}
				
				text {
					color: #fff;
					font-size: 28rpx;
					font-weight: 600;
				}
			}
			
			.card-desc {
				color: rgba(255, 255, 255, 0.9);
				font-size: 24rpx;
			}
			
			.card-bg {
				position: absolute;
				top: 0;
				left: 0;
				right: 0;
				bottom: 0;
				z-index: 1;
				
				&.bg-1 {
					background: linear-gradient(45deg, #12c2e9, #c471ed);
				}
				
				&.bg-2 {
					background: linear-gradient(45deg, #ff6b6b, #feca57);
				}
			}
		}
	}
	
	.section-3 {
		margin-top: 30rpx;
		display: grid;
		grid-template-columns: 2fr 1fr;
		gap: 20rpx;
		
		.points-card {
			background: linear-gradient(135deg, #a8e063 0%, #56ab2f 100%);
			padding: 30rpx;
			border-radius: 20rpx;
			color: #fff;
			
			.points-info {
				display: flex;
				align-items: center;
				margin-bottom: 10rpx;
				
				.points-label {
					font-size: 28rpx;
				}
				
				.points-value {
					font-size: 40rpx;
					font-weight: bold;
					margin-left: 20rpx;
				}
			}
			
			.points-desc {
				font-size: 24rpx;
				opacity: 0.9;
			}
			
			.points-btn {
				margin-top: 20rpx;
				display: inline-block;
				padding: 10rpx 30rpx;
				background: rgba(255, 255, 255, 0.2);
				border-radius: 30rpx;
				font-size: 24rpx;
			}
		}
		
		.qr-card {
			background: #fff;
			border-radius: 20rpx;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			box-shadow: 0 4rpx 20rpx rgba(0, 0, 0, 0.08);
			
			image {
				width: 60rpx;
				height: 60rpx;
				margin-bottom: 10rpx;
			}
			
			text {
				font-size: 24rpx;
				color: #666;
			}
		}
	}
</style>
