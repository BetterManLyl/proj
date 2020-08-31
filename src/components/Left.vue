<template>
  <div>
    <div class="title" @click="onclickc(12)">{{message}}</div>
    <ul class="menu">
      <li>笔记本电脑</li>
      <li>手机</li>
      <li>服饰</li>
      <li>手表</li>
      <li>书籍</li>
      <li>玩具</li>
      <li>小家电</li>
      <li>学习用品</li>
      <li>办公用品</li>
      <li>旅游必备</li>
      <li>游戏卡通</li>
    </ul>
  </div>
</template>

<style>
.title {
  width: 100px;
  color: red;
}
.menu li {
  list-style: none;
  height: 50px;
  margin-bottom: 2px;
  background-color: white;
  line-height: 50px;
}
</style>

<script>
export default {
  created() {
    console.log("created");
  },
  mounted() {},
  data() {
    return {
      message: "热门推荐",
    };
  },
  methods: {
    onclickc(message) {
      console.log(message);
    },
  },
};
</script>