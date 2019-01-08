<template>
<div class="wrapper">
  <ul class="tab_Title">
      <li @click="Lent" :class="{activityStyle: lent==true}">我要租</li>
      <li @click="Buy" :class="{activityStyle: buy==true}">我要买 <span>(随时可退)</span></li>
  </ul>
  <div class="blank"></div>
  <swiper class="swiper" :indicator-dots="true" :autoplay="autoplay" :interval="interval" :duration="duration" style="height:170px;margin-bottom:35px">
    <block v-for="item in imgUrls" :index="index" :key="key">
        <swiper-item style="border-radius:5px">
            <img :src="item.url" style="width:375px;height:170px">
        </swiper-item>
    </block>
  </swiper>
  <div class="activity" v-if="lent">
      <div>免费保修</div>
      <div>随买随时退</div>
      <div>首次支付12月享9折</div>      
  </div>
  <div class="actiPepople" v-if="lent">
      已经超过100万+人在参与租赁生活
  </div>
  <ul class="mid_classify" v-if="buy">
      <li>
          <i class="iconfont icon-kefu"></i>
          <div>有疑问找客服</div>
      </li>
      <li>
          <i class="iconfont icon-ai226"></i>
          <div>一年随时保底退换</div>
      </li>
      <li>
           <i class="iconfont icon-hongbao"></i>
          <div>现金退款</div>
      </li>
  </ul>
  <div class="content" v-if="buy">
      优惠专区
      <span>查看全部</span>
  </div>
  <div class="content" v-if="lent">
      商品推荐
      <span>查看更多</span>
  </div>
  <div class="commodityMap">
        <div class="detailWrapper">
            <img src="/static/imgs/apple.jpg" alt="">
            <div>苹果(Apple)电脑iMacbook</div>
        </div>
        
  </div>
  <div class="content" v-if="buy">
      猜你喜欢
      <span>查看全部</span>
  </div>
  <div class="content" v-if="lent">
      分享有礼
  </div>
  <div class="thingList">
      <div class="leftImg">
         <img src="/static/imgs/apple.jpg" alt="">
      </div>
      <div class="rightContent">
            <p class="p1">二手9成新苹果Macbook Pro 15154545</p>
            <p class="p2"><span class="span1">无忧购￥10605</span><span class="span2">市场价格11888</span></p>
            <p class="p3">无忧保障期内保底可退￥6939</p>
      </div>
  </div>
   <div class="thingList">
      <div class="leftImg">
         <img src="/static/imgs/apple.jpg" alt="">
      </div>
      <div class="rightContent">
            <p class="p1">二手9成新苹果Macbook Pro 15154545</p>
            <p class="p2"><span class="span1">无忧购￥10605</span><span class="span2">市场价格11888</span></p>
            <p class="p3">无忧保障期内保底可退￥6939</p>
      </div>
  </div>
   <div class="thingList">
      <div class="leftImg">
         <img src="/static/imgs/apple.jpg" alt="">
      </div>
      <div class="rightContent">
            <p class="p1">二手9成新苹果Macbook Pro 15154545</p>
            <p class="p2"><span class="span1">无忧购￥10605</span><span class="span2">市场价格11888</span></p>
            <p class="p3">无忧保障期内保底可退￥6939</p>
      </div>
  </div>
</div>
</template>
<script>
export default {
 data () {
    return {
     imgUrls: [
      {url:'https://ss2.bdstatic.com/70cFvnSh_Q1YnxGkpoWK1HF6hhy/it/u=1161149267,3646555459&fm=27&gp=0.jpg'},
      {url:'https://ss1.bdstatic.com/70cFuXSh_Q1YnxGkpoWK1HF6hhy/it/u=2683717104,3302829015&fm=27&gp=0.jpg'}
    ],
    buy:false,   
    lent:true,   
    indicatorDots: true,
    autoplay: true,
    interval: 5000,
    duration: 1000,
    }
  },
  
  methods:{
     Buy() {
          this.buy = true;
          this.lent = false;
      },
      //点击切换到买
      Lent(){
           this.buy = false;
           this.lent = true;
      }
    }
}
</script>

<style scope="scoped" lang="scss">
    $colorgray:#ACACAC;
    $coloryellow:#E89D0D;
    .wrapper{
        padding: 20px;
        .tab_Title{
            display: flex;
            position: fixed;
            left: 0;
            top: 0;
            padding-left: 20px;
            background: white;
            z-index: 10;
            width: 375px;
            li{
                padding-right: 40px;
                color: #ACACAC;
                font-size: 20px;
                margin-bottom: 15px;
                span{
                    font-size: 15px;
                }
            }
        }
        .blank{
            height: 20px;
        }
        .activity{
            display: flex;
            margin-bottom: 30px;
            div{
                flex: 1;
                color: $colorgray;
                font-size: 12px;
            }
        }
        .actiPepople{
            background: #F7F7F7;
            font-size: 12px;
            line-height: 30px;
            transform: scale(0.8,0.8);
            color:$colorgray;  
            margin-bottom: 35px;
        }
        .mid_classify{
            display: flex;
            margin-bottom: 35px;
            li{
               flex: 1;
               i{
                  font-size:20px;
                  color: #F69100; 
                }
               div{
                   margin-top: 10px;
                   font-size: 12px;
                   color: #B1B1B1;
               } 
               img{
                   width: 20px;
                   height: 20px
               }
            }
        }
        .content{
            margin-bottom: 50px;
            font-size: 15px;
            text-align: left;   
            span{
                float: right;
                font: 12px;
                color: #BFBFBF;
            }
        }
        .commodityMap{
            display: flex;
            .detailWrapper{
                width: 50%;
                margin-bottom: 60px;
                img{
                    width: 90px;
                    height:80px; 
                    margin-bottom: 30px;
                }
                div{
                    font-size: 12px;
                    overflow:hidden;
                    text-overflow:ellipsis;
                    white-space:nowrap
                }
            }
        }
        .thingList{
            padding: 28px 10px 28px 28px;
            display: flex;
            align-items: center;
            border-bottom: 18px solid #FAFAFA;
            .leftImg{
                img{
                    width: 90px;
                    height: 60px;   
                    margin-right: 35px;      
                }
            }
            .rightContent{
               flex: 1;
               width: 0;
                .p1{
                    text-align: left;
                    font-size: 15px;
                    white-space: nowrap;
                    text-overflow: ellipsis;
                    overflow: hidden;
                    margin-bottom: 10px;
               }
               .p2{
                    text-align: left;
                    font-size: 15px;
                    white-space: nowrap;
                    text-overflow: ellipsis;
                    overflow: hidden;
                    margin-bottom: 40px;
                    .span1{
                        color:$coloryellow;
                        margin-right: 2px;
                    }
                    .span2{
                        color: $colorgray;        
                    }
               }
               .p3{
                   background: #FEF5E9; 
                   font-size: 12px;
                   color: $coloryellow;
               }
            }
        }
        .activityStyle{
            color: $coloryellow!important;
        }
    }    
</style>
