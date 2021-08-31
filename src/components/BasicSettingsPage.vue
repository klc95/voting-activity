<template>
    <div class="container">
          <div class="header">
              <div class="title">三步创建您的投票活动</div>
              <div class="settings">
                  <div class="settings_item" style="width: 33.3333%">
                      <div class="head"></div>
                      <div class="txt"></div>
                      <div class="tail"><i></i></div>
                  </div>
                  <div class="settings_item" style="width: 33.3333%">
                      <div class="head"></div>
                      <div class="txt"></div>
                      <div class="tail"><i></i></div>
                  </div>
                  <div class="settings_item" style="width: 33.3333%">
                      <div class="head"></div>
                      <div class="txt"></div>
                  </div> 
              </div>
          </div>


          <div class="main"></div>
          <div class="footer"></div>
    </div>
</template>

<script>
export default {
   name:'BasicSettingsPage'
}
</script>

<style scoped lang="less">
    .container{
        padding: 0px 50px 40px 50px;
        max-width: 1104px;
        margin: 80px auto;
        position: relative;  
    }

    .header{
        height: 154px;
        .title{
            padding: 38px 38px 57px;
            text-align: center;
            font-size: 36px;
            font-family: PingFangSC-Light;
        }
        .settings{
            width: 100%;
            margin: auto;
            font-size: 0;
            line-height: 1.5;
            margin-bottom: 50px;
        }
    }
</style>