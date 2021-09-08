<template>
  <div style="background-color: #f3f4f7">
    <Navigation />
    <div style="height: 20px"></div>
    <div class="container">
      <div class="header ivu-row">
        <span class="headline">投票活动列表</span>
        <Button type="primary"><span>+</span>&nbsp;新建投票</Button>
      </div>

      <div class="main ivu-row">
        <div v-for="(item,index) in items" :key="item.id">
          <div class="list-item" @mouseenter="enter(index)" @mouseleave="leave(index)">
            <div class="wrap">
              <div class="image ivu-col">
                <img
                  src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEsAAABLCAMAAAAPkIrYAAACUlBMVEVHcEzPztTPz9fT09zQz9XPz9XQztXb29vPztXQ0NXQz9T////////QztXQztT////S0uHb29v////Q0NjQz9XPztTQz9XQztXQztXbztvj4+PZ2dnS0tnR0dXQz9XT097Q0NbR0dfV1dXS0tfPz9TQz9TV1dXQz9XQztTPztXQ0NXPz9jQz9TY2NjPz9TQz9XV1dXTz9bQztXX19fQ0NfR0ejQztXPz9bV1dXQ0NXQz9bf39/Qz9XPztXQztTQ0NbSztfQ0NbQz9XPztXQztXSztbRz9bQ0NTPz9/QztXPz9XQz9XPz9bR0dXPztXT09vQz9XQz9TR0dXQztXPztXR0dbSz9bQz9TQztXPztTQ0NbW1tbQ0NXV1dXQz9XSztXS0tbQztTd3d3R0dj////Qz9XQztXT09jPztXUz9nQz9XPztXVztXPz9XPz9TRztTQztXR0dvPztXPztXR0dfRz9TT09rR0djQ0NXPz9fPz9bPz9XQz9XQ0NXS0tfPztTR0dbQz9bRz9bPztXPz9XQz9XPz9bY2NjQ0NXPz9XQz9XQ0NXQztXQztXQztTQz9XQ0NXQztXPz9bPztTm5ubR0dbPz9TQ0NXQztXPz9XQztTQ0NXT09jQztXQ0NXW1tbPz9TQztXPztXQ0NnQz9TQzdTQz9bR0NbRz9XQ0NbR0NbQz9XQztXQz9TQz9TRz9XQztXPztXPztXRztXPz9XRz9TQz9XQz9TRz9bR0dXPz9XPz9XV1dXRztbQz9XQz9XQ0NTPz9XQ0NfQz9XQz9TPztS2oeIVAAAAxXRSTlMA9UAdyIbHDvA23QUBeK0DEQcCQa76/eeYFQkUKEOfF1FNEi3KxBj+suGRO+8N0PkGRcwTJgvNcAxsjgj4wad8P1fT9vdEmncQkqW0dj3xI5njN7zgOErul9ZdH4Ek5Ek+uA8nBN6NLvw18uYqtcVZqBzssVNfKSFcIHVVznI50TKUy+Srw6Yak+rJVpOi19hmc6DcCiyhZ7cwg2I0wmgZa9L7G/Tnusir3sfUvbmJep3r5W7aj9++b07Aux5e7c9xlkzzswr8IYcAAAOzSURBVFjDrdb1XxsxFADw18HKBh2lHRTpug5333Bn+ASZMQaDbQzm7u7u7u7u7nv/10JLuyRn5e7yAz1yd9/PS/LyLgC+t3l20KkFlCVi2x19KH8kLdBPJyrvqS7YAGUMCArWAXNTADpgHkoH7D+lGaMpjRhLacJ4imChBDugknoQwPY5bTjTro66fZ/rvIBYqI56/DCa692PWK/DXLnaPgzXQK1IslD9cXhcQ1RrVo+nboSiLV39AC00BZMQo7XNVWWQ52qqDc+c1UKtwyLv9WnE81mewq1iBaNqE7zXkdMQq1oHri5dU9xOEslgNg9enOsi9frQsp7kRMW9KUWtbPRgCUnobbKYBAUT4tuKvf+0NuxIm9ne7AiVxaQogIIoYV+QHMbkVargbp3Jd4yJ6qZhPne7GTf6HBlDWbp6s7j79ZNMvg6TnatCnC0WeqQAEyvbLFX8usoKjs+juYc2JTeIYf5muRV8g58WfUHDHO5Fe0a+cJgk3xbJUFFLwoOxeqETFnAvWkTGHYE4WSav8hGri5zQXdpfVcG/msoFOxyxt5ilHtEperH6HdnO40oWj02euJSz4jLXc9SIqyx1D69QD4TcIH+yw5b0wVdbCmcl1PDUSG6AHZfN/NSkfSchOcNmQYFgimLlKNcA7UwuzsVvZBHi0ZH6ik+NtbbNCpRfYAT9QgV+hIAP+BxyMwwctso/Vp6CkLw6pmQZM0PfYwqJNRV5TCEqYfJEli2+dZ38jgkPeyvEosvlqIE2uUiwfwk1LvfHT653QXuJAgWlJbEiFAnZ+ouL7CBLWYyCKhpTIUqBdSw3Z9wA4YV4Qe6mh9nkoZYxq8lT8AwNItSWxOH0Dsh2U8YsOjUEFLxEHCW0YprGcz2E+pMZDbk5lZIUdN4VxUgzmVjqr305wczSFMAwgzhmqo2gsPQc/A3py8tBjpLE0rcaJ9BzljMxG7IUKEkshF0TF6ZESQ8TCrZRwwzxr1SmvJi1o8/PzFZx+qNm9YVyYwv3ppFTy5Sy6VRqlFsVK4M45mnHmCOI0zREyo3F78o/epgcz+KoBdzQMmuoFMHiHK5fRzJiMDXjeYVDpqgidAJxBvVJ1kABTO/HUqajJsWkkgIIRhtzlok3jFFLwSnEYUzV2K6aIl9FPML3TTWpouAkM/mutnPKblUUpCB28ht9jzoqMg2nDXnjSDRyLmvUiRIpQaopIaaB4jFNFItppGhMM/Uf04HyYLpQbuyJPtTgN0Afipy6e1qS5vv++D+qV3kcIGoKTAAAAABJRU5ErkJggg=="
                />
              </div>
              <div class="title ivu-col">
                <div class="txt">{{ item.title }}</div>
                <div class="draft">草稿</div>
              </div>
              <div
                class="operation ivu-col"
                v-show="item.seen"
                @mouseenter="enter(index)"
                @mouseleave="leave(index)"
              >
                <div class="inner">
                  <div class="complie">
                    <i class="el-icon-edit"></i>
                    <span>继续编辑</span>
                  </div>
                  <div class="delete">
                    <i class="el-icon-delete"></i>
                    <span>删除</span>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>

      <div class="footer ivu-row">
        <Page :total="2"></Page>
      </div>
    </div>
  </div>
</template>

<script>
import Navigation from "../Navigation";

export default {
  name: "VotingList",
  data() {
    return {
      seen: false,
      items: [
        { id: 1, title: "新建投票活动", seen: false },
        { id: 2, title: "新建投票活动", seen: false },
        { id: 3, title: "新建投票活动", seen: false },
        { id: 4, title: "新建投票活动", seen: false },
        { id: 5, title: "新建投票活动", seen: false },
        { id: 6, title: "新建投票活动", seen: false },
        { id: 7, title: "新建投票活动", seen: false },
        { id: 8, title: "新建投票活动", seen: false },
        { id: 9, title: "新建投票活动", seen: false },
        { id: 10, title: "新建投票活动", seen: false },
      ],
    };
  },
  methods: {
    enter(index) {
      this.items[index].seen = true;
    },
    leave(index) {
      this.items[index].seen = false;
    },
  },
  components: {
    Navigation,
  },
};
</script>

<style scoped lang="less">
@import "./VotingList.less";
</style>