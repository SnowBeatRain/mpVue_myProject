<template>
    <div class="nav">
        <div v-for="(l,i) in data" :key="i">
          <p><i class="icon iconfont icon-daohangshouye"></i></p>
          <P>{{l.name}}</P>
        </div>
        <!-- <div>
          <P>图标</P>
          <P>首页</P>
        </div>
         <div>
          <P>图标</P>
          <P>购物车</P>
        </div>
         <div>
          <P>图标</P>
          <P>我的</P>
        </div> -->
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
<style scoped lang='scss'>
.nav {
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 50px;
  background-color: red;
  display: flex;
  justify-content: space-around;
  text-align: center;
}
</style>