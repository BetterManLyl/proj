<template>
  <div id="show">
    <ul class="goodList">
      <li v-for="goods in list">
        <img v-bind:src="goods.img" />
        <p>{{goods.goodName}}</p>
      </li>
    </ul>
  </div>
</template>

<style>
.goodList li {
  width: 200px;
  height: 200px;
  list-style: none;
  float: left;
  font-size: 9px;
  color: red;
  margin-bottom: 30px;
}
.goodList img {
  width: 180px;
  height: 180px;
}
</style>
<script>
export default {
  name: "Goodlist",
  data() {
    var _this = this;
    var url="";
    if (_this.goodId == 1) {
        url = "json/bjb.json";
      } else if (_this.goodId == 2) {
        url = "json/sj.json";
      }else{
        url = "json/bjb.json";
      }
    this.$http.get(url).then(function (res) {
      _this.list = res.data;
    });

    return {
      list: [],
    };
  },
  //父组件向子组件传值
  props: {
    goodId: Number,
  },
  //监听父组件向子组件传值变化
  watch: {
    goodId() {
      var obj = this;
      var url = "";
      if (obj.goodId == 1) {
        url = "json/bjb.json";
      } else if (obj.goodId == 2) {
        url = "json/sj.json";
      }else{
        url = "json/bjb.json";
      }
      this.$http.get(url).then(function (res) {
        obj.list = res.data;
      });

      return {
        list: [],
      };
    },
  },
};
</script>