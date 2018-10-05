<template>
  <div id="app">
    <div>
        <home-header :city='selCity'></home-header>
        <home-swiper :swiperList='swiperList'></home-swiper>
        <home-icons :iconList='iconList'></home-icons>
        <home-recommend :recommendList='recommendList'></home-recommend>
        <home-weekend :weekendList='weekendList'></home-weekend>
    </div>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'

export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      selCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {
    getHomeInfo () {
      // axios.get('/static/mock/index.json')
      axios.get('/api/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if (res.ret) {
        const data = res.data
        // console.log('获取index.json: ', data)
        this.selCity = data.city
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  },
  mounted () {
    this.getHomeInfo()
  }
}
</script>

<style>

</style>
