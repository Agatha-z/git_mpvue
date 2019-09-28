<template>
  <div class="indexContainer">
    <swiper @change="handleCount" class="swiperBig" :indicator-dots="index !==3" indicator-color indicator-active-color="#e43a3d">
		<swiper-item>
			<img src="/static/images/1.jpg" alt="">
		</swiper-item>
		<swiper-item>
			<img src="/static/images/2.jpg" alt="">
		</swiper-item>
		<swiper-item>
			<img src="/static/images/3.jpg" alt="">
		</swiper-item>
		<swiper-item>
			<img src="/static/images/4.jpg" alt="">
		</swiper-item>
    </swiper>
	<button  @click="toBooks" class="btn" v-show="index === 3">开始体验</button>
  </div>
</template>

<script>
export default {
	data() {
		return {
			index: 0
		}
	},
	methods: {
		handleCount(e) {
			// console.log(e);
			this.index = e.mp.detail.current
		},
		toBooks(){
			wx.switchTab({
				url:'/pages/books/main'
			})
		}
	}
}
</script>

<style lang="less" scope="this api replaced by slot-scope in 2.5.0+">
.indexContainer{
	height: 100%;
	.swiperBig{
		width: 100%;
		height: 100%;
		swiper-item{
			width: 100%;
			height: 100%;
			img{
				width: 100%;
				height: 100%;
			}
		}
	}
	.btn{
		width: 280rpx;
		height: 80rpx;
		background: rgba(255, 255, 255, 0.5);
		line-height: 80rpx;
		text-align: center;
		position: absolute;
		left: 50%;
		margin-left: -140rpx;
		bottom: 40rpx;
	}
}
</style>