<template>
  <div class="container" @click="clickHandle('test click', $event)">
    <div class="userinfo" @click="bindViewTap">
      <img
        class="userinfo-avatar"
        v-if="userInfo.avatarUrl"
        :src="userInfo.avatarUrl"
        background-size="cover"
      >
      <div class="userinfo-nickname">
        <card :text="userInfo.nickName"></card>
      </div>
    </div>

    <div class="usermotto">
      <div class="user-motto">
        <card :text="motto"></card>
      </div>
    </div>
    <i-card full title="卡片标题" extra="额外内容,znjkldkl;asf hsd;lak hnz这个了拉萨了；索拉卡和好难受啊啊" thumb="https://i.loli.net/2017/08/21/599a521472424.jpg">
      <view slot="content">内容不错</view>
      <view slot="footer">尾部内容</view>
    </i-card>
    <img src="https://i.loli.net/2017/08/21/599a521472424.jpg" alt="">
    <form class="form-container">
      <input type="text" class="form-control" v-model="motto" placeholder="v-model">
      <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy">
      <input type="text" class="form-control" v-model.lazy="motto" placeholder="v-model.lazy">
    </form>
    <a href="/pages/counter/main" class="counter">去往tmdd示例页面</a>
    <a href="/pages/logs/main" class>查看日志</a>
    <a href="/pages/first/main" class>fisrt</a>
    <a href="/pages/second/main" class="counter">second</a>
  </div>
</template>

<script>
import card from "@/components/card";

export default {
  data() {
    return {
      motto: "Hello World",
      userInfo: {}
    };
  },

  components: {
    card
  },

  methods: {
    bindViewTap() {
      const url = "../logs/main";
      wx.navigateTo({ url });
    },
    getUserInfo() {
      // 调用登录接口
      wx.login({
        success: () => {
          wx.getUserInfo({
            success: res => {
              this.userInfo = res.userInfo;
            }
          });
        }
      });
    },
    clickHandle(msg, ev) {
      console.log("clickHandle:", msg, ev);
    }
  },

  created() {
    // 调用应用实例的方法获取全局数据
    this.getUserInfo();
  }
};
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
