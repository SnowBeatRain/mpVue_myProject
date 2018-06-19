<template>
    <div>shop
        <Nav-tab :data='navData'></Nav-tab>
    </div>
</template>
<script>
import NavTab from '@/components/nav'
export default {
  data () {
    return {
      navData: [
        {
          name: '首页',
          path: '/pages/index/main',
          active: false
        },
        {
          name: '购物车',
          path: '/pages/shop/main',
          active: true
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
    }
  },
  components: {
    NavTab
  }
}
</script>
<style scoped>
</style>