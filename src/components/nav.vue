<template>
  <div class="nav">
    <div v-for="(l,i) in data" :key="i">
      <a  class="nav_list active" :href="l.path" v-if="l.active">
          <p>
            <i class="icon iconfont icon-daohangshouye"></i>
          </p>
          <P>{{l.name}}</P>
      </a>
      <a  class="nav_list" :href="l.path" v-else>
          <p>
            <i class="icon iconfont icon-daohangshouye"></i>
          </p>
          <P>{{l.name}}</P>
      </a>
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
    return {}
  },
  mounted () {
    console.log(this.data)
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
  .active{
    color: red!important;
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
