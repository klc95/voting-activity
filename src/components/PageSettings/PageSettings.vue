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
        <div class="second_step">
          <div class="part" style="margin-left: -8px; margin-right: -8px">
            <div class="block">
              <div class="voting_theme">
                <div class="item_title">投票主题</div>
                <div class="item_input">
                  <el-color-picker
                    v-model="color5"
                    show-alpha
                    :predefine="predefineColors"
                  >
                  </el-color-picker>
                </div>
              </div>
              <div class="voting_layout">
                <div class="item_title">页面布局</div>
                <div class="item_input">
                  <div class="radio_group">
                    <div class="radio_item">
                      <input type="radio" name="votingItem_layout" />
                      <span>每行1列投票项</span>
                    </div>
                    <div class="radio_item">
                      <input type="radio" name="votingItem_layout" />
                      <span>每行2列投票项</span>
                    </div>
                  </div>
                </div>
              </div>
              <div class="voting_items_ranking">
                <div class="item_title">投票项排序</div>
                <div class="item_input">
                  <el-select v-model="value" clearable placeholder="请选择">
                    <el-option
                      v-for="item in options"
                      :key="item.value"
                      :label="item.label"
                      :value="item.value"
                    >
                    </el-option>
                  </el-select>
                </div>
              </div>
              <div class="voting_custom_sharing">
                <div class="item_title">自定义分享</div>
                <div class="item_input">
                  <div class="sharing_picture">
                    <div class="sharing_info">分享图片</div>
                    <input type="file" />
                  </div>

                  <div class="sharing_headline">
                    <div class="sharing_info">分享标题</div>
                    <Input
                      v-model="value3"
                      placeholder="请输入分享标题，必填"
                      style="width: 300px"
                      maxlength="30"
                    />
                  </div>

                  <div class="sharing_digest">
                    <div class="sharing_info">分享摘要</div>
                    <Input
                      v-model="value4"
                      type="textarea"
                      :autosize="{ minRows: 8, maxRows: 5 }"
                      placeholder="新建投票活动进行中，快来投票吧"
                      style="width: 280px"
                      maxlength="100"
                    >
                    </Input>
                  </div>
                </div>
              </div>
              <div class="display_setup">
                <div class="item_title">显示设置</div>
                <div class="item_input">
                  <div class="setting_item">
                    <div class="setting_info">投票说明</div>
                    <div class="item" style="width: 150px">
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票名称</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票简介</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票规则</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票时间</span>
                      </div>
                    </div>
                  </div>
                  <div class="setting_item">
                    <div class="setting_info">投票统计</div>
                    <div class="item">
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>活动倒计时</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票统计</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>排行榜入口</span>
                      </div>
                    </div>
                  </div>
                  <div class="setting_item">
                    <div class="setting_info">投票项</div>
                    <div class="item">
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票项搜索框</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票项序号</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票项介绍</span>
                      </div>
                      <div class="item_checked">
                        <input type="checkbox" />
                        <span>投票项票数</span>
                      </div>
                    </div>
                  </div>
                  <p>
                    *投票活动创建完成后，您仍然可以对每一项内容与设置进行修改
                  </p>
                </div>
              </div>
            </div>
          </div>
          <div class="mobile_preview"><MobilePreview /></div>
        </div>
      </div>
      <div class="footer">
        <Button style="width: 146px; height: 46px; margin-right: 24px"
          >上一步</Button
        >
        <Button type="primary">保存并进入下一步</Button>
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from "../Navigation";
import MobilePreview from "../MobilePreview";
export default {
  name: "PageSettings",
  data() {
    return {
      value3: "",
      value4: "",
      color5: "#1e90ff",
      predefineColors: [
        "#ff4500",
        "#ff8c00",
        "#ffd700",
        "#90ee90",
        "#00ced1",
        "#1e90ff",
        "#c71585",
        "rgba(255, 69, 0, 0.68)",
        "rgb(255, 120, 0)",
        "hsv(51, 100, 98)",
        "hsva(120, 40, 94, 0.5)",
        "hsl(181, 100%, 37%)",
        "hsla(209, 100%, 56%, 0.73)",
        "#c7158577",
      ],
      options: [
        {
          value: "选项1",
          label: "得票数目",
        },
        {
          value: "选项2",
          label: "编号顺序",
        },
        {
          value: "选项3",
          label: "编号逆序",
        },
      ],
    };
  },
  components: {
    Navigation,
    MobilePreview,
  },
};
</script>

<style scoped lang="less">
@import "./PageSettings.less";
</style>

<style>
.el-upload-dragger {
  width: 300px !important;
}

.el-select {
  width: 336px;
}

.ivu-input-inner-container {
  width: 280px;
}
</style>