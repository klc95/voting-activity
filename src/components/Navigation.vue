<template>
  <div class="container">
    <a class="logo" href="https://www.kuaizhan.com/" alt='快'>
      <img src="//cdn.kuaizhan.com/res/homepage/images/logo-kuaizhan-new.png?v=5.0" />
    </a>
    <div class="vote_form">
      <span>投票</span>
      <i>x</i>
    </div>
    <div class="right_part">
      <div class="right_content">
        <div class="item">工作台</div>
        <div class="item">投票列表</div>
        <div class="item">升级套餐</div>
        <div class="item">开放平台</div>
        <div class="item">快站大学</div>
      </div>
      <div class="user">133xxxxxxxx</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navigation",
};
</script>

<style scoped>
    .container{
      box-sizing: border-box;
      width: 100%;
      height: 60px;
      color: #333333;
      box-shadow: 0 2px 4px 0 rgb(0 0 0 / 10%);
      background: #fff;
      position: fixed !important;
      top: 0;
      left: 0;
      right: 0;
      z-index: 101;
      display: flex;
      align-items: center;
      font-size: 14px;
      font-family: Roboto,PingFang SC,Lantinghei SC,Microsoft Yahei,Hiragino Sans GB,Microsoft Sans Serif,WenQuanYi Micro Hei,sans-serif; 
    }

    .logo{
      display: inline-block;
      position: relative;
      vertical-align: middle;
      cursor: pointer;
    }

    .logo::after{
      content: '';
      position: absolute;
      right: 0;
      top: 0;
      height: 28px;
      width: 0;
      border-right: 1px solid #ededf0;
    }

    .logo img{
      margin: 0 24px;
    }

    .vote_form{
      margin-left: 20px;
    }

    .right_part{
      display: flex;
      align-items: center;
      position: absolute;
      right: 0;
      width: 500px;
      height: 60px;
    }

    .right_content{
      display: flex;
      align-items: center;
      justify-content: space-around;
      width: 397px;
    }

    .user {
      margin-right: 24px;
    }

    .vote_form:hover, .item:hover {
      cursor: pointer;
      color: blue;
    }
</style>