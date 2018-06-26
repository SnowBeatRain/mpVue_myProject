<template>
  <div class="nav">
    <div v-for="(l,i) in data" :key="i">
      <a  class="nav_list" :class=" {active:l.active}" @click='clickTo(l.path)'>
          <p>
            <i class="icon iconfont icon-daohangshouye"></i>
          </p>
          <P>{{l.name}}</P>
      </a>
      <!-- <a  class="nav_list" :href="l.path" v-else>
          <p>
            <i class="icon iconfont icon-daohangshouye"></i>
          </p>
          <P>{{l.name}}</P>
      </a> -->
    </div>
  </div>
</template>
<script>
export default {
  props: {
    data: {
      type: Array,
      required: true
    }
  },
  data () {
    return {
      // 是否是当前页  如果是那么点击tabbar不跳转
      isNowPath: false
    }
  },
  mounted () {
    // console.log(this.data)
  },
  methods: {
    clickTo (e) {
      console.log(this.$root.$mp)
      var pages = getCurrentPages()
      var currentPage = pages[pages.length - 1]
      var urlP = currentPage.route
      console.log(urlP)
      // var nowUrl = this.$root.$mp.appOptions.path
      console.log(e)
      if (this.comparePath(urlP, e)) {
      } else {
        wx.navigateTo({ url: e })
      }
    },
    // 比较当前页和点击跳转的页面是否为同一个
    comparePath (old, n) {
      // n.substr(1) 截取掉n的第一位/ 用于判断old路径
      if (old === n.substr(1)) {
        return true
      } else {
        return false
      }
    }
  }
}
</script>
<style scoped lang="scss">
$background_color: #1989df;
$font_color: #fff;
.nav {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  background-color: $background_color;
  text-align: center;
  .active {
    color: red !important;
  }
  .nav_list {
    color: $font_color;
  }
  .icon {
    font-size: 40rpx;
  }
  .nav_list {
    width: 25%;
    height: 100%;
    float: left;
  }
}
</style>
