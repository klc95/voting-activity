<template>
<div style='background-color:#F3F4F7'>
  <Navigation/>
  <div class="container">
    <div class="create_steps">
      <div class="title">三步创建您的投票活动</div>
      <div class="settings">
        <div class="settings_item" style="width: 45%">
          <div class="head">
            <div class="head_inner">1</div>
          </div>
          <div class="main">基础设置</div>
          <div class="tail"><i></i></div>
        </div>
        <div class="settings_item" style="width: 44%">
          <div class="head"><div class="head_inner">2</div></div>
          <div class="main">页面设置</div>
          <div class="tail"><i></i></div>
        </div>
        <div class="settings_item" style="width: auto">
          <div class="head"><div class="head_inner">3</div></div>
          <div class="main">高级设置</div>
        </div>
      </div>
    </div>
    <div class="panel">
      <div class="first_step">
        <div class="part_one" style="margin-left: -8px; margin-right: -8px">
          <div class="block">
            <div class="voting_name">
              <div class="item_title">
                <span style="color: red">*</span>
                投票名称
              </div>
              <div class="item_input">
                <Input
                  v-model="value1"
                  placeholder="请输入您的投票活动名称，必填"
                  style="width: 300px"
                  maxlength="30"
                >
                </Input>
                <!-- <div style='color:red'>
                    <p>请输入投票名称</p>
                    <p>0/30</p>
                </div> -->
              </div>
            </div>
            <div class="voting_duration">
              <div class="item_title">
                <span style="color: red">*</span>
                投票时间
              </div>
              <div class="item_input">
                <Date-picker
                  type="datetimerange"
                  placeholder="选择日期和时间"
                  style="width: 300px"
                >
                </Date-picker>
              </div>
            </div>
            <div class="voting_profile">
              <div class="item_title">投票简介</div>
              <div class="item_input">
                <Input
                  v-model="value2"
                  type="textarea"
                  :autosize="{ minRows: 6.7, maxRows: 8 }"
                  placeholder="请输入您的投票活动简介，选填"
                  style="width: 300px"
                >
                </Input>
              </div>
            </div>
            <div class="voting_picture">
              <div class="item_title">宣传图片</div>
              <div class="item_input">
                <el-upload
                  class="upload-demo"
                  drag
                  action="https://jsonplaceholder.typicode.com/posts/"
                  multiple
                >
                  <i class="el-icon-upload"></i>
                  <div class="el-upload__text">
                    <p>该图片将展示在投票页面的顶端</p>
                    <p style="font-size: 12px">
                      建议图片宽度大于640像素，不超过4M
                    </p>
                    <p style="font-size: 12px">
                      支持拓展名: .jepg .jpg .png .gif等格式
                    </p>
                  </div>
                </el-upload>
              </div>
            </div>
            <div class="voting_items">
              <div class="item_title">投票项</div>
              <div class="item_radio">
                <div class="radio_group">
                  <div class="radio_item">
                    <input type="radio" name="skip" /><span>跳转详情页</span>
                  </div>
                  <div class="radio_item">
                    <input type="radio" name="skip" /><span>跳转其他页</span>
                  </div>
                  <div class="radio_item">
                    <input type="radio" name="skip" /><span>无跳转</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mobile_preview"><MobilePreview /></div>

        <div class="part_two">
          <div style="margin-left: 116px; max-width: 720px">
            <div class="header">
              <div class="select_wrap">
                <span><input type="checkbox" /></span>
              </div>
              <div class="order"><span>序号</span></div>
              <div class="pic">图片</div>
              <div class="name_profile">名称和简介</div>
            </div>
            <div class="add_items">
              <i
                class="el-icon-plus"
                style="font-size: 40px; color: #9b9b9b"
              ></i>
              <p>添加投票项</p>
            </div>
            <p>* 投票活动创建完成后，您仍然可以对每一项内容与设置进行修改</p>
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <Button type="primary">保存并进入下一步</Button>
    </div>
  </div>
</div>
</template>

<script>
import Navigation from "./Navigation";
import MobilePreview from "./MobilePreview";


export default {
  name: "BasicSettingsPage",
  data() {
    return {
      value1: "",
      value2: "",
    };
  },
  components: {
    Navigation,
    MobilePreview
  },
};
</script>


<style scoped lang="less">
.container {
  padding: 0px 50px 40px 50px;
  max-width: 1104px;
  margin:60px auto 0;
  position: relative;
  box-sizing: border-box;
}

.create_steps {
  height: 154px;
  margin-bottom: 50px;
  .title {
    padding: 38px 38px 57px;
    text-align: center;
    font-size: 36px;
    font-family: PingFangSC-Light;
  }
  .settings {
    width: 100%;
    margin: auto;
    font-size: 0;
    line-height: 1.5;
    margin-bottom: 50px;
    display: flex;
    flex-wrap: nowrap;
    :first-child {
      .head {
        .head_inner {
          display: block;
          width: 26px;
          height: 26px;
          line-height: 24px;
          margin-right: 8px;
          text-align: center;
          border: 1px solid #ccc;
          border-radius: 50%;
          font-size: 14px;
          text-align: center;
          border-color: #2d8cf0;
          background-color: #2d8cf0;
          color: #fff;
        }
      }
    }

    .settings_item {
      display: flex;
      vertical-align: top;
      position: relative;
      flex-wrap: nowrap;
      text-align: center;
    }
  }

  .head {
    .head_inner {
      display: block;
      width: 26px;
      height: 26px;
      line-height: 24px;
      margin-right: 8px;
      text-align: center;
      border: 1px solid #ccc;
      border-radius: 50%;
      font-size: 14px;
      text-align: center;
      color: #ccc;
    }
  }

  .main {
    margin-top: 3px;
    margin-bottom: 0px;
    padding-right: 0;
    font-size: 14px;
    font-weight: 700;
    color: #666;
  }

  .tail {
    width: 350px;
    position: absolute;
    left: 100px;
    top: 13px;
    padding: 0 0 0 10px;
    i {
      display: inline-block;
      width: 100%;
      height: 1px;
      vertical-align: top;
      background: #e9eaec;
      border-radius: 1px;
      position: relative;
      ::after {
        content: "";
        width: 0;
        height: 100%;
        background: #e9eaec;
        opacity: 0;
        position: absolute;
        top: 0;
      }
    }
  }
}

.panel {
  background-color: #fff;
  box-shadow: 0 2px 4px 0 rgb(0 0 0 / 10%);
  position: relative;
  min-height: 600px;
  padding-top: 68px;
  .first_step {
    padding: 0 40px 70px 40px;
    background-color: #fff;
  }
}

.block {
  width: 50%;
  .voting_name,
  .voting_duration {
    display: flex;
    margin-bottom: 28px;
    height: 36px;
    .item_title {
      font-family: Roboto, PingFang SC, Lantinghei SC, Microsoft Yahei,
        Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans-serif;
      color: #151515;
      letter-spacing: 0;
      font-size: 14px;
      min-width: 100px;
      text-align: right;
      line-height: 32px;
    }
    .item_input {
      margin-left: 16px;
      width: calc(100% - 100px);
      line-height: 32px;
    }
  }

  .voting_profile {
    display: flex;
    flex-wrap: nowrap;
    height: 150px;
    margin-bottom: 28px;
    .item_title {
      font-family: Roboto, PingFang SC, Lantinghei SC, Microsoft Yahei,
        Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans-serif;
      color: #151515;
      letter-spacing: 0;
      font-size: 14px;
      min-width: 100px;
      text-align: right;
      line-height: 32px;
    }
    .item_input {
      margin-left: 16px;
      width: calc(100% - 100px);
      line-height: 32px;
    }
  }

  .voting_picture {
    display: flex;
    flex-wrap: nowrap;
    height: 219px;
    margin-bottom: 28px;
    .item_title {
      font-family: Roboto, PingFang SC, Lantinghei SC, Microsoft Yahei,
        Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans-serif;
      color: #151515;
      letter-spacing: 0;
      font-size: 14px;
      min-width: 100px;
      text-align: right;
      line-height: 32px;
    }
    .item_input {
      margin-left: 16px;
      line-height: 32px;
    }
  }
  .voting_items {
    display: flex;
    flex-wrap: nowrap;
    margin-bottom: 28px;
    .item_title {
      font-family: Roboto, PingFang SC, Lantinghei SC, Microsoft Yahei,
        Hiragino Sans GB, Microsoft Sans Serif, WenQuanYi Micro Hei, sans-serif;
      color: #151515;
      letter-spacing: 0;
      font-size: 14px;
      min-width: 100px;
      text-align: right;
      line-height: 32px;
    }
    .item_radio {
      margin-left: 16px;
      width: calc(100% - 100px);
      height: 32px;
      margin-left: 16px;
      .radio_group {
        display: flex;
        align-items: center;
        line-height: 32px;
        .radio_item {
          display: flex;
          align-items: center;
          span {
            margin-left: 5px;
            margin-right: 5px;
          }
        }
      }
    }
  }
}
.mobile_preview {
  position: absolute;
  bottom: -25px;
  left: 300px;
  transform: scale(0.375);
}

.part_two {
  position: relative;
  margin-left: 0;
  margin-right: 0;
  height: auto;
  zoom: 1;
  display: block;
  margin-top: 10px;
  .header {
    border: 1px solid #e1e0e7;
    display: flex;
    padding: 0px 8px;
    height: 36px;
    line-height: 36px;
    margin-bottom: none;
    border-bottom: none;
    .select_wrap {
      padding: 0px 14px;
      input {
        display: inline-block;
        width: 14px;
        height: 14px;
        vertical-align: sub;
        position: relative;
        border: 1px solid #d7dde4;
        border-radius: 2px;
        cursor: pointer;
      }
    }
    .order {
      width: 60px;
      min-width: 60px;
      max-width: 60px;
      padding: 0px 14px;
      position: relative;
      text-overflow: ellipsis;
      white-space: nowrap;
    }
    .pic {
      max-width: 102px;
      min-width: 102px;
      padding: 0px 14px;
    }
    .name_profile {
      width: 360px;
      min-width: 360px;
      max-width: 360px;
    }
  }
  .add_items {
    border: 1px solid #e1e0e7;
    text-align: center;
    cursor: pointer;
    padding: 33px 0;
    height: 120px;
  }
}

.footer {
  margin: auto;
  text-align: center;
  margin-top: 50px;
  font-size: 18px;
  Button {
    font-size: 18px;
    width: 285px;
    height: 46px;
  }
}

</style>

<style>
  .el-upload-dragger{
    width: 300px!important;
  }
</style>