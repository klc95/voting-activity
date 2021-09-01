<template>
<div>
    <div class='container'>
        <div class='wrap'>
            <div class='activity_title'>新建投票活动</div>
            <div class="activity_info">
                <div class='activity_profile'>
                    <div class='voting_rules'>投票规则：<span class='ruleContent'>每天可投十票</span></div>
                    <div class='voting_time'>投票时间：<span class='time'>2021-08-23 00:00 至 2021-08-30 00:00</span></div>
                </div>
                <div class='activity_status'><span>活动暂停中</span></div>
                <div class='activity_data'>
                    <div class='competitor_data '>
                        <div class='num'>0</div>
                        <div class='tip'>参与选手</div>
                    </div>
                    <div class='competitor_data'>
                        <div class='num'>0</div>
                        <div class='tip'>累计投票</div>
                    </div>   
                </div>
                <div class='ranking'>
                    <img src='data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABkAAAAZCAMAAADzN3VRAAAByFBMVEVHcEz5xRP5xRP7wRP8vxP6xBP5xRP+2DL81Sv8vxP7wBP7wBP8vhP6wxP5xRP6xBP8vxP8vhP7whP6wxP7whP5xhP8vxP7wBP8vxP7wBP7wBP7wRP8vxP7wRP7wRP6xBP7wBP6xBP5xhP5xhP/3Dr5xhP/3Dr5xhP/2zj+2jX/2zj5xxP+2DL5xhP5xxP4yBP+2jX5xxP4yBP+2DL4yRP5xxP5xxP4yBP5xxP81Sv4yRP4yBP4yxb4yBP+2DL4yxb4yRP4yBP4yxb4yBP4yRP81Cj81Sv4yxb4yRP5zBn70SL70iX5zhz5zBn4yRP5zBn4yxb70iX81Cj4yRP4yxb5zBn6zx/4yRP91y75zBn4yxb6zx/70SL5zhz81Cj70iX70SL5zhz81Cj6zx/5zhz81Sv81Sv70iX5zBn4yxb81Cj81Sv5zhz5zBn81Cj70iX70iX70SL70SL6zx/70iX6zx/5zhz81Cj70SL5zhz5zBn6zx/5zBn4yxb5zhz91y781Sv70iX/3Dr/2zj+2jX+2DL81Cj70SL6zx/5zhz5zBn8vhP4yRP4yxb4yBP5xxP8vxP5xhP5xRP7wBP7wRP6xBP7whP6wxOnd/WpAAAAf3RSTlMAcv0PgSz6cGDXD1KvcGXC5596YGXQ5syOEtva/gbEM125ecuXFn9zmZCA9MESfvl/8PyvcgUD+3SfxsbBGGkIYhKqvM9JjrTVHu0ecAsU9wz8MA660bHL8A/AS5U47BZW4fC1A+jyzmEB3vBXEfkJuNRnmCbGRwOHAVE83KvUxnU0JAAAAQhJREFUGBl1wQNDxGAABuA3bpdt27Yu27ZtG7c0tK26hb9bq7u2r9bzQJVwTUqCXcoNKQ12qbekHKioTxl3pHyKoqpw9Y9hWBZoutRCaqTpxTXMTgIN96ReHG2uYomZQhtD6NnCPrONcXYaaGX1doBd9hhj3BwwyOntAQfcGeZn+Am083rrOOQvT4BlYaCjRdDpGtk4F04BrPRLTeYKSVPbPSpdQNXZLJYViJrqenGoD18qy+Vs+UdesVxXA5vCrPRHTW5JETSJcYHP3+KTM/GLg6PVanX1goFo79dYFxjyfPeHMb+3ABhyCn+JisRfoTFhiqIEu7uBEGIKerKJ8DE5Q+PxoOcL1Qd5RLICJGFsaQAAAABJRU5ErkJggg=='/>
                    <span>查看榜单</span>
                </div>
            </div>
        </div>
        <div class='searching_wrap'>
            <input class='searching_input' 
                    type='text' 
                    placeholder='请输入投票编号或名称'
                />
            <i class='iconfont'>&#xe647;</i>
        </div> 
        <div class='voting_items'>暂无投票项</div>
    </div>
 
 </div>   

</template>

<script>
import '../icon/iconfont.css'
export default {
   name:'MobilePreview'
}
</script>

<style scoped lang="less">
   .container{
        box-sizing: border-box;
        // transform: scale(0.375);
        // transform-origin: top right;
        overflow-x: hidden;   
        border-radius: 6px;
        border: 2px solid #EDEDF0;
        overflow: scroll;
        overflow-x: hidden;
        background-color: #F3F4F7;
        width: 750px;
        height: 1340px;
        .wrap{
            background: #FFFFFF;
            box-shadow: 0 3px 14px rgba(0, 0, 0, 0.04)
     }
   }

   .activity_title{
        font-size: 48px;
        color: #111111;
        letter-spacing: 0;
        line-height: 55px;
        margin: 0px 30px 30px;
        display: block;
        padding-top: 18px;
        word-break: break-all;
   }

   .activity_info{
        background: #FFFFFF;
        box-shadow: 0 3px 14px rgba(0, 0, 0, 0.04);
    }

    .activity_profile{
        padding: 30px;
        position: relative;
        overflow: hidden;
        z-index: 1;
        font-size: 28px;
        color: #111111;
        ::after{
            content: '';
            height: 1px;
            position: absolute;
            bottom: 0;
            left: 16px;
            right: 16px;
            background-color: #E0E0E0;
        }
        span{
            font-size: 28px;
            color: #999999;
            letter-spacing: 0;
            line-height: 42px;
        }
    }

    .activity_status{
        font-size: 28px;
        color: #111111;
        letter-spacing: 0;
        margin-right: 10px;
        padding: 30px;
        position: relative;
        overflow: hidden;
        z-index: 1;
        ::after{
            content: '';
            height: 1px;
            position: absolute;
            bottom: 0;
            left: 16px;
            right: 16px;
            background-color: #E0E0E0;
        }
    }

    .activity_data{
        display: flex;
        padding: 30px 0;
        height: 124px;
        border-bottom: 1px solid #E0E0E0;
        box-sizing: border-box;
        justify-content: space-around;
    }

    .competitor_data{
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        position: relative;
        width: 50%;
        ::after{
            content: '';
            width: 1px;
            position: absolute;
            height: 41px;
            background-color: #D8D8D8;
            top: 12px;
            right: 0;
        }
        .num{
            font-size: 30px;
            color: #111111;
            letter-spacing: 0;
            line-height: 30px;
        }
        .tip{
            font-size: 28px;
            color: #999999;
            letter-spacing: 0;
            line-height: 42px;
        }
    }

    .ranking{
        padding: 32;
        font-size: 30px;
        color: #111111;
        letter-spacing: 0;
        line-height: 30px;
        position: relative;
        height: 55px;
        display: -ms-flexbox;
        display: flex;
        justify-content: center;
        align-items: center;
        img{
            width: 25px;
            height: 25px;
            margin-right: 8px;
        }
    }

    .searching_wrap{
        background: #FFFFFF;
        box-shadow: 0 3px 14px rgb(0 0 0 / 4%);
        border-radius: 2px;
        margin-left: 16px;
        margin-right: 16px;
        margin-top: 20px;
        padding: 35px;
        .searching_input{
            font-size: 30px;
            width: 80%;
            padding: 2px 8px;
            border: none;
        }
            .iconfont{
                font-size: 55px !important;
        }
    }

    .voting_items{
        font-size: 30px;
        color: #CFCED4;
        text-align: center;
        margin: 80px 0 0 0;
        padding-bottom: 300px;
    }








   

</style>