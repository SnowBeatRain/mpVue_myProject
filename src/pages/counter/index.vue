<template>
  <div class="counter-warp">
    <p>Vuex counter：{{ count }}</p>
    <p>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </p>

    <Nav-tab :data='navData'></Nav-tab>
  </div>
</template>

<script>
// Use Vuex
import store from './store'
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
          active: true
        },
        {
          name: '我的',
          path: '/pages/mine/main',
          active: false
        }
      ]
    }
  },
  computed: {
    count () {
      return store.state.count
    }
  },
  components: {
    NavTab
  },
  methods: {
    increment () {
      store.commit('increment')
    },
    decrement () {
      store.commit('decrement')
    }
  }
}
</script>

<style>
.counter-warp {
  text-align: center;
  margin-top: 100px;
}
.home {
  display: inline-block;
  margin: 100px auto;
  padding: 5px 10px;
  color: blue;
  border: 1px solid blue;
}
</style>
