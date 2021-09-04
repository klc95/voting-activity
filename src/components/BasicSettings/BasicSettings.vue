<template>
  <div style="background-color: #f3f4f7">
    <Navigation />
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
                      <input type="radio" name="skip" />
                      <span>跳转详情页</span>
                    </div>
                    <div class="radio_item">
                      <input type="radio" name="skip" />
                      <span>跳转其他页</span>
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
import Navigation from "../Navigation";
import MobilePreview from "../MobilePreview";

export default {
  name: "BasicSettings",
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
 @import './BasicSettings.less';
</style>

<style>
.el-upload-dragger {
  width: 300px !important;
}
</style>