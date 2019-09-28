<template>
    <div id="booksContainer">
        <swiper  class="swiperBig" circular indicator-dots indicator-color indicator-active-color="#e43a3d">
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
        <div class="listContainer">
            <div class="listHeader">
                <span>全部商品</span>
                <span>></span>
            </div>
            <ul class="booksList">
                <li>
                    <img src="/static/images/1.jpg" alt="">
                    <p>《打发发达》</p>
                    <p>猪八戒</p>
                </li>
                <li>
                    <img src="/static/images/2.jpg" alt="">
                    <p>《打发发达》</p>
                    <p>猪八戒</p>
                </li>
                <li>
                    <img src="/static/images/3.jpg" alt="">
                    <p>《打发发达》</p>
                    <p>猪八戒</p>
                </li>
                <li>
                    <img src="/static/images/4.jpg" alt="">
                    <p>《打发发达》</p>
                    <p>猪八戒</p>
                </li>
            </ul>
        </div>  
    </div>
</template>

<script>
export default {
    
}
</script>

<style lang="less" scope="this api replaced by slot-scope in 2.5.0+">
    #booksContainer{
        // width: 100%;
        .swiperBig{
            width: 100%;
            height: 400rpx;
            img{
                width: 100%;
                height: 100%;
            }
        }
        .listContainer{
            .listHeader{
                display: flex;
                justify-content: space-between;
                padding: 20rpx;
                & span:last-child{
                    color: #02a774;
                }
            }
            .booksList{
                display: flex;
                flex-wrap: wrap;
                li{
                    width: 50%;
                    display: flex;
                    flex-direction: column;
                    align-items: center;
                    padding: 10rpx 0;
                    border-bottom: 1rpx solid #eee;
                    &:nth-child(2n+1){
                        border-right: 1rpx solid #eeeeee;
                        box-sizing: border-box;
                    }
                    img{
                        width: 200rpx;
                        height: 200rpx;
                    }
                    p{
                        line-height: 50rpx;
                    }
                }
            }
        }
    }
</style>