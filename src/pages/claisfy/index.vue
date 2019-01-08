<template>
  <div class="claisfy">
    <div class="clasLeft">
      <ul>
        <li v-for="(item,index) in leftMessage" :key="index" @click="clickBanner(index)" :class="{clickAcrtive:index==acticeColor}">{{item.title}}</li>
      </ul>
    </div>
     <scroll-view
          style="height:510px"
          scroll-y
     >
        <ul class="clasRight">
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li> 
         <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li> 
         <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li> 
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li>
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li>
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li>
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li>
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li>
        <li>
          <div class="div1">
              <img src="/static/imgs/apple.jpg" alt="">
          </div>
          <div class="div2">
            鑻规灉iMac 27 鑻卞�镐竴鍙版槸鏈€濂界殑
          </div>
          <div class="div3">
            鏈堢�燂骏458.0
          </div>
        </li> 
    </ul>
     </scroll-view>
  </div>
</template>

<script>
    export default{
      data(){
        return{
          acticeColor:0,
          leftMessage:[{
            title:'绗旇�版湰'
          },{
            title:'鎵嬭��'
          },{
            title:'涓€浣撴満'
          },{
            title:'鍙板紡鐢佃剳'
          },{
            title:'鎵撳嵃鏈�'
          },{
            title:'鎶曞奖浠�'
          },{
            title:'骞虫澘'
          },{
            title:'绌烘皵鍑€鍖栧櫒'
          },{
            title:'鍔炲叕'
          }]
        }
      },
      methods: {
        clickBanner(index){
          this.acticeColor = index;
        }
      },
    }
</script>

<style lang="scss" scope>
    $coloryellow:#E89D0D; 
   .claisfy{
      margin-top: 10px;
      display: flex;
      .clasLeft{
        width: 86px;
        margin-right: 13px;
        li{
          width: 86px;
          color: #686868;
          line-height: 43px;
          font-size: 14px;
          background: #F5F5F5;
          margin-bottom: 2px;
        }
      }
      .clasRight{
        overflow: auto;
        flex: 1;
        display: flex;
        flex-wrap: wrap;
        padding-top: 20px;
        li{
          .div1{
             width: 120px;
             text-align: center;
             border: 1px solid #E1E1E1;
             img{
               padding: 20px 17px;
               width: 90px;
               height: 70px;
             }
           }
           .div2{
              margin-top: 15px;
              width: 120px;
              font-size: 12px;
              overflow:hidden;
              text-overflow:ellipsis;
              white-space:nowrap
           }
           .div3{
             width: 120px;
             font-size: 13px;
             color: $coloryellow; 
             margin-top: 10px;
             margin-bottom: 20px;
           }
        }
      }
      .clickAcrtive{
        background: white!important;
        color: $coloryellow!important;
      }
   }
</style>
