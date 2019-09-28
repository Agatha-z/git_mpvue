<template>
    <div class="personalContainer">
        <div class="header">
            <img class="avatar" :src="userInfo.avatarUrl?userInfo.avatarUrl:'/static/images/1.jpg'" alt="">
            <button open-type="getUserInfo" @getuserinfo="handleUserInfo" class="userName">{{userInfo.nickName?userInfo.nickName:'登录'}}</button>
        </div>  
        <button @click="scan">扫码看书</button>
    </div>
</template>

<script>
export default {
    data(){
        return {
            userInfo: {}
        }
    },
    created(){
        wx.getUserInfo({
            success: (e) =>{
                console.log(e)
                this.userInfo = e.userInfo;
            },
            fail: () =>{

            }
        })
    },
    methods:{
        handleUserInfo(e){
            console.log(e);
            if(e.mp.detail.rawData){
                this.userInfo = JSON.parse(e.mp.detail.rawData)
            }
        },
        scan(){
            wx.scanCode({
                success: (e) =>{
                    console.log(e)
                },
                fail: (e) =>{
                    console.log(e)
                }
            })
        }
    }
}
</script>

<style lang="less" scope="this api replaced by slot-scope in 2.5.0+">
    .personalContainer{
        .header{
            display: flex;
            align-items: center;
            padding: 40rpx;
            background: #02a774; 
            img{
                width: 100rpx;
                height: 100rpx;
                border-radius: 50%;
                margin: 0 40rpx;
                // vertical-align: middle;
            }
            .userName{
                // display: inline-block;
                height: 60rpx;
                line-height: 60rpx;
                text-align: center;
                // vertical-align: middle;
                margin: 0;
                background: rgba(255, 255, 255, 0.5)
            }
        }
    }
</style>