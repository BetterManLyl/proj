<template>
  <div class="main">
    <div class="left">
      <Left></Left>
    </div>
    <div class="right">
      
      <div class="top">
        <img @click="getListData()" src="../../public/img/title.jpg" />
      </div>
      <div class="bottom">
<Right></Right>

      </div>
    </div>
  </div>
</template>

<style>
* {
  padding: 0;
  margin: 0;
}
.left {
  width: 100px;
  float: left;
  margin-right: 10px;
}
.right {
  width: 1000px;
  float: left;
  margin-right: 10px;
}
.main {
  width: 1200px;
  margin: 20px auto;
}
.top img {
  height: 200px;
  width: 1000px;
}
.left,
.right {
  background-color: #f5f5f5;
  height: 600px;
}
</style>

<script>
import Left from "../components/Left";
import Right from "../components/Right";
export default {
  components: {
    Left,Right
  },
  data() {
    return {
      message: "message",
    };
  },
  methods: {
    testCallAndroid() {
      window.android.takePhoto();
      alert("打电话");
    },
    getListData(){//网络请求数据
            var url = "http://www.phonegap100.com/appapi.php?a=getPortalList&catid=20&page=1";
             //jsonp请求，需要后台接口支持jsonp
             // this.$http.jsonp(api).then((response)=>{
            //get请求
            this.$http.get(url).then((response=>{

            }))
            this.$http.get(url).then((response)=>{
                console.log("请求到的数据："+response);
                this.list = response.body.result;
            },(error)=>{
                console.log("请求错误："+error);
            })
        },
  },
};
</script>