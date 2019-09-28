<template>
    <div id="searchBookContainer">
        <div class="header">
            <input v-model="searchContent" type="text" placeholder="请输入书名" placeholder-class="placeholder">
            <span @click="searchContent = ''" v-show="searchContent" class="clear">X</span>
        </div>    
    </div>
</template>

<script>
export default {
    data(){
        return {
            searchContent:''
        }
    },
    methods:{
        // clear(){
        //     this.searchContent = ''
        // }
    }
}
</script>

<style lang="less" scope="this api replaced by slot-scope in 2.5.0+">
    #searchBookContainer{
        .header{
            position: relative;
            width: 80%;
            height: 80rpx;
            border-bottom: 1rpx solid #02a774;
            margin: 0 auto;
            input{
                width: 100%;
                height: 100%;
            }
            .placeholder{
                text-align: center;
                color: #02a774;
                font-size: 28rpx;
            }
            .clear{
                position: absolute;
                right: 20rpx;
                bottom: 0;
                font-size: 40rpx;
                height: 100%;
                line-height: 80rpx;
                z-index: 99
            }
        }
    }
</style>