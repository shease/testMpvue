<template>
  <div class="person">
    <div class="header">
      <div class="heaLeft">
        <div class="div1" @click="getSetting" v-if="disagree">登陆</div>
        <!-- 登陆之后显示名字 -->
        <div class="div1" v-if="agree">{{loginName}}</div>
        <div class="div2">获取免押金额度</div>
      </div>
      <div class="headRight">
        <img src="/static/imgs/person.png" v-if="disagree">
        <!-- 登陆之后显示头像 -->
        <img :src="loginPicture" alt v-if="agree">
      </div>
    </div>
    <ul class="listContent">
      <li>
        <i class="iconfont icon-hongbao"></i>
        <div>余额</div>
        <p>
          <i class="iconfont icon-youjiantou target"></i>
        </p>
      </li>
      <li v-for="(item,index) in nanContent" :key="index">
        <i :class="item.icon"></i>
        <div>{{item.contnet}}</div>
        <p>
          <i class="iconfont icon-youjiantou target"></i>
        </p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginPicture: "",
      loginName: "",
      disagree: true,
      agree: false,
      nanContent: [
        {
          icon: "iconfont icon-dingdan",
          contnet: "订单"
        },
        {
          icon: "iconfont icon-tubiao201",
          contnet: "地址"
        },
        {
          icon: "iconfont icon-qiaquan",
          contnet: "卡券"
        },
        {
          icon: "iconfont icon-liwu",
          contnet: "合伙人"
        },
        {
          icon: "iconfont icon-xiugai",
          contnet: "补充资料"
        },
        {
          icon: "iconfont icon-wenti-m",
          contnet: "帮助"
        }
      ]
    };
  },
  onShow() {
    var that = this;
    wx.getSetting({
      success: function(res) {
        if (res.authSetting["scope.userInfo"]) {
          wx.getUserInfo({
            success: function(res) {
              console.log(res);
              //用户已经授权过
              that.loginPicture = res.userInfo.avatarUrl;
              that.loginName = res.userInfo.nickName;
              that.disagree = false;
              that.agree = true;
            }
          });
        }
      }
    });
  },
  methods: {
    // 检查用户是否授权
    getSetting() {
      var that = this;
      wx.getSetting({
        success: function(res) {
          if (res.authSetting["scope.userInfo"]) {
            wx.getUserInfo({
              success: function(res) {
                console.log(res);
                that.loginPicture = res.userInfo.avatarUrl;
                that.loginName = res.userInfo.nickName;
                that.disagree = false;
                that.agree = true;
              }
            });
          } else {
            var url = "../agree/main";
            wx.navigateTo({ url });
            console.log("用户还未授权过");
          }
        }
      });
    }
  }
};
</script>

<style lang="scss" scope>
.person {
  padding-left: 15px;
  .header {
    display: flex;
    margin-bottom: 50px;
    .heaLeft {
      width: 125px;
      .div1 {
        text-align: left;
        width: 125px;
        font-style: 25px;
        color: #526ec6;
        margin-bottom: 20px;
      }
      .div2 {
        text-align: left;
        width: 125px;
        font-size: 12px;
        color: #526ec6;
      }
    }
    .headRight {
      flex: 1;
      text-align: right;
      img {
        width: 80px;
        height: 80px;
        margin-right: 30px;
      }
    }
  }
  .listContent {
    li {
      display: flex;
      margin-bottom: 45px;
      i {
        font-size: 20px;
      }
      div {
        margin-left: 15px;
        font-size: 15px;
      }
      p {
        flex: 1;
        text-align: right;
        margin-right: 8px;
        i {
          font-size: 15px;
        }
      }
    }
  }
}
</style>
