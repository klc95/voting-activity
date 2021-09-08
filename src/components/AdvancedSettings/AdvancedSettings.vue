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
        <div class="third_step">
          <div class="part_one" style="margin-left: -8px; margin-right: -8px">
            <div class="block">
              <div class="voting_rule">
                <div class="item_title">投票规则</div>
                <div class="item_input">
                  <Select v-model="model1" style="width: 200px">
                    <Option
                      v-for="item in rules"
                      :value="item.value"
                      :key="item"
                    >
                    </Option>
                  </Select>
                  <el-input-number
                    v-model="num"
                    controls-position="right"
                    @change="handleChange"
                    :min="1"
                    :max="10"
                  >
                  </el-input-number>
                  <div>票</div>
                </div>
              </div>

              <div class="voting_application">
                <div class="item_title">允许报名</div>
                <div class="item_input">
                  <i-switch v-model="switch1" @click="change1">
                    <span slot="open">开</span>
                    <span slot="close">关</span>
                  </i-switch>
                  <Poptip
                    trigger="hover"
                    width="250"
                    content="开启后，用户可报名参赛"
                    placement="right-start"
                  >
                    <div>??</div>
                  </Poptip>
                  <div v-show="switch1" class="hidden_part">
                    <div style="margin-top: 10px; margin-bottom: 20px">
                      <span style="color: red">*</span>
                      报名时间
                      <Date-picker
                        type="datetimerange"
                        placeholder="选择日期和时间"
                        style="width: 300px"
                      >
                      </Date-picker>
                    </div>
                    <div>
                      <span style="margin-right: 16px">自动通过</span>
                      <i-switch v-model="switch2" @click="change2"></i-switch>
                      <Poptip
                        trigger="hover"
                        width="350"
                        content="开启后用户的报名信息自动通过，直接显示在投票列表中"
                        placement="right-start"
                      >
                        <div>??</div>
                      </Poptip>
                    </div>
                    <div>
                      <span style="margin-right: 16px">报名设置</span>
                      <div class="application_wrapper">
                        <div class="application_profile">
                          <div class="header">
                            <div class="tip-minor register-name">输入项</div>
                            <div class="tip-minor register-type">类型</div>
                            <div class="tip-minor register-required">
                              是否必填
                            </div>
                          </div>
                          <div class="detail">
                            <div class="tip-minor register-name">名称</div>
                            <div class="tip-minor register-type">单行文本</div>
                            <div class="tip-minor register-required">必填</div>
                          </div>
                          <div class="detail">
                            <div class="tip-minor register-name">详细介绍</div>
                            <div class="tip-minor register-type">多行文本</div>
                            <div class="tip-minor register-required">选填</div>
                          </div>
                          <div class="detail">
                            <div class="tip-minor register-name">图片</div>
                            <div class="tip-minor register-type">图片</div>
                            <div class="tip-minor register-required">选填</div>
                          </div>
                        </div>
                        <div class="application_reminder">
                          <div class="text-tip">
                            <div class="tip-icon">!</div>
                            <span class="tip"
                              >可在下方添加其他报名信息，用于信息采集。用户所填内容不在投票页面展示</span
                            >
                          </div>
                        </div>
                        <div class="add_application_info">
                          <div class="inner">
                            <div>+</div>
                            <span>添加报名信息</span>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
              <div class="voting_limitation">
                <div class="item_title">时段限定</div>
                <div class="item_input">
                  <div style="margin-bottom: 20px">
                    <i-switch v-model="switch3" @click="change3">
                      <span slot="open">开</span>
                      <span slot="close">关</span>
                    </i-switch>
                    <Poptip
                      trigger="hover"
                      width="250"
                      content="开启后，用户只能在限定时段内进行投票"
                      placement="right-start"
                    >
                      <div>??</div>
                    </Poptip>
                  </div>
                  <div v-show="switch3" class="hidden_part">
                    <Col span="12">
                      <TimePicker
                        format="HH:mm"
                        type="timerange"
                        placement="bottom-end"
                        placeholder="时段"
                        style="width: 300px"
                      ></TimePicker>
                    </Col>
                  </div>
                </div>
              </div>
              <div class="voting_modify_document">
                <div class="item_title">修改文案</div>
                <div class="item_input">
                  <i-switch v-model="switch4" @click="change4">
                    <span slot="open">开</span>
                    <span slot="close">关</span>
                  </i-switch>
                  <div v-show="switch4" class="hidden_part">
                    <div class="modify_item">
                      <span>&emsp;&emsp;&nbsp;按钮文字</span>
                      <Input
                        v-model="value"
                        clearable
                        style="width: 200px"
                        maxlength="30"
                      />
                    </div>
                    <div class="modify_item">
                      <span>&emsp;&emsp;&nbsp;投票成功</span>
                      <Input
                        v-model="value"
                        clearable
                        style="width: 200px"
                        maxlength="30"
                      />
                    </div>
                    <div class="modify_item">
                      <span>当日投票超限</span>
                      <Input
                        v-model="value5"
                        clearable
                        style="width: 200px"
                        maxlength="30"
                      />
                    </div>
                    <div class="modify_item">
                      <span>投票总量超限</span>
                      <Input
                        v-model="value6"
                        clearable
                        style="width: 200px"
                        maxlength="30"
                      />
                    </div>
                    <div class="modify_item">
                      <span>&emsp;&nbsp;投票未开始</span>
                      <Input
                        v-model="value7"
                        clearable
                        style="width: 200px"
                        maxlength="30"
                      />
                    </div>
                    <div class="modify_item">
                      <span>&emsp;&nbsp;投票已结束</span>
                      <Input v-model="value8" clearable style="width: 200px" />
                    </div>
                    <div class="modify_item">
                      <span>投票活动暂停</span>
                      <Input v-model="value9" clearable style="width: 200px" />
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="mobile_preview"><MobilePreview /></div>
      </div>

      <div class="footer">
        <Button style="margin-right: 24px"> 上一步 </Button>
        <Button type="primary">完成</Button>
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from "../Navigation";
import MobilePreview from "../MobilePreview";

export default {
  name: "AdvancedSettings",
  data() {
    return {
      rules: [
        {
          value: "每人每天可投",
        },
        {
          value: "每人一共可投",
        },
      ],
      num: 1,
      switch1: false,
      switch2: false,
      switch3: false,
      switch4: false,
    };
  },
  methods: {
    change1() {
      this.switch1 = !this.switch1;
    },
    change2() {
      this.switch1 = !this.switch1;
    },
    change3() {
      this.switch1 = !this.switch1;
    },
    change4() {
      this.switch1 = !this.switch1;
    },
  },
  components: {
    Navigation,
    MobilePreview,
  },
};
</script>


<style scoped lang="less">
@import "./AdvancedSettings.less";
</style>

<style>
.el-upload-dragger {
  width: 300px !important;
}

.ivu-select-selection {
  height: 38px !important;
  margin-right: 15px;
}

.el-input-number {
  width: 80px !important;
  height: 38px;
  margin-right: 5px;
}
.el-input__inner {
  height: 38px !important;
}

.ivu-switch {
  margin-right: 10px;
}

.ivu-input-inner-container {
  margin-left: 10px;
  text-align: left;
  width: 300px;
}

.ivu-select-placeholder{
  display: block;
  height: 36px!important;
  line-height: 36px!important;
}
</style>