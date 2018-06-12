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
      userInfo: {},
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
        name: '首页'
      },
      {
        name: '购物车'
      },
      {
        name: '发布'
      },
      {
        name: '我的'
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
$base_color: red;
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

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
