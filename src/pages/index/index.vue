<template>
  <div class="container">

    <a href="/pages/counter/main" class="counter">去往Vuex示例页面</a>
    <a href="/pages/shop/main" class="counter">去往shop页面</a>    
    <a href="/pages/mine/main" class="counter">去往mine页面</a>
    <Nav-tab :data='navData'></Nav-tab>
  </div>
</template>

<script>
// 引入组件需要注意：避免使用header  nav 等语义化标签作为组件名
import card from '@/components/card'
import NavTab from '@/components/nav'
export default {
  data () {
    return {
      motto: 'Hello World',
      navData: []
    }
  },

  components: {
    card,
    NavTab
  },

  methods: {
    bindViewTap () {
      const url = '../logs/main'
      wx.navigateTo({ url })
    }
  },

  created () {
    // 调用应用实例的方法获取全局数据
    this.navData = [
      {
        name: '首页',
        path: '/pages/index/main',
        active: true
      },
      {
        name: '购物车',
        path: '/pages/shop/main',
        active: false
      },
      {
        name: '发布',
        path: '/pages/counter/main',
        active: false
      },
      {
        name: '我的',
        path: '/pages/mine/main',
        active: false
      }
    ]
    this.$http
      .get('/test', { xx: 6 })
      .then(d => {
        // 输出请求数据
        console.log(d.data)
        // 输出响应头
        console.log(d.header)
      })
      .catch(err => {
        console.log(err.status, err.message)
      })
  }
}
</script>

<style scoped lang='scss'>
$base_color: #1989df;
.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid $base_color;
}

.counter {
  display: inline-block;
  margin: 10px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
