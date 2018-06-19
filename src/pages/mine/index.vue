<template>
    <div>
      
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
          active: true
        }
      ]
    }
  },
  components: {
    NavTab
  }
}
</script>
<style scoped lang="scss">
$base-color: red;
</style>