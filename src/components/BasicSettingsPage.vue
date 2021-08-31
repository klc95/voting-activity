<template>
    <div class="container">
          <div class="header">
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
                  <div class="part_one" style="margin-left:-8px;margin-right:-8px">
                      <div class="block" style="padding-left:-8px;padding-right:-8px">
                          <div class="item">
                                <div class="item_title">
                                  <span style="color:red">*</span>
                                  投票名称
                                </div>
                               <div class="item_input">
                                  <input type='text' placeholder="请输入您的投票活动名称，必填"/>
                                  <!-- <div style='color:red'>
                                      <p>请输入投票名称</p>
                                      <p>0/30</p>
                                    </div> -->
                              </div>
                          </div>
                          <div class="item">
                                <div class="item_title">
                                  <span style="color:red">*</span>
                                  投票时间
                                </div>
                               <div class="item_input">
                                  <input type='text' placeholder="请输入您的投票活动名称，必填"/>
                                  <!-- <div style='color:red'>
                                      <p>请输入投票名称</p>
                                      <p>0/30</p>
                                    </div> -->
                              </div>
                          </div>

                          
                      </div>
                  </div>

                  <div class="part_two"></div>
              </div>
          </div>

          <div class="footer"></div>
    </div>
</template>

<script>
import {  } from 'element-ui';
import './BasicSettingPage.less'
export default {
   name:'BasicSettingsPage'
}
</script>


<style scoped lang="less">
    
</style>