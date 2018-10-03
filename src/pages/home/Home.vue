<template>
  <div id="app">
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <div>this is Home</div>
    </div>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper
  }
}
</script>

<style>

</style>
