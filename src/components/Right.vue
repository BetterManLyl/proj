<template>
  <div>
    <div v-if="kk==1">
      <Goodlist :goodId="1"></Goodlist>
    </div>
    <div v-else-if="kk==2">
      <Goodlist :goodId="2"></Goodlist>
    </div>
    <div v-else-if="kk==3">
      <Goodlist :goodId="3"></Goodlist>
    </div>
    <div v-else-if="kk==4">
      <Goodlist :goodId="4"></Goodlist>
    </div>
     <div v-else>
      <Goodlist :goodId="0"></Goodlist>
    </div>
  </div>
</template>
<script>
import Msg from "./msg.js";
import Goodlist from "./Goodlist";
export default {
  data() {
    return {
      kk: 0,
    };
  },
  mounted: function () {
    var _this = this;
    Msg.$on("val", function (m) {
      _this.kk = m;
    });
  },

  components: {
    Goodlist,
  },
};
</script>