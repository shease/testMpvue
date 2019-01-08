<template>
 <div>
   <!--2222-->
    <button open-type="getUserInfo" @getuserinfo="bindGetUserInfo" @click="getUserInfo1">閼惧嘲褰囬弶鍐�妾�</button>  
 </div>
</template>

<script>
 export default {
   data () {
     return {
        
     }
   },
   methods: {
     bindGetUserInfo(e) {
      // console.log(e.mp.detail.rawData)
      if (e.mp.detail.rawData){
        //閻�銊﹀煕閹稿�夌啊閸忎浇锟藉憡宸块弶鍐╁瘻闁斤拷
        console.log('閻�銊﹀煕閹稿�夌啊閸忎浇锟藉憡宸块弶鍐╁瘻闁斤拷')
        var url = "../person/main"
        wx.switchTab({url})
    } else {
        //閻�銊﹀煕閹稿�夌啊閹锋帞绮烽幐澶愭尦
        console.log('閻�銊﹀煕閹稿�夌啊閹锋帞绮烽幐澶愭尦')
      }
     }
   },
   components: {

   }
 }
</script>

<style>

 
</style>
