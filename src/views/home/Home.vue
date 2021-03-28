<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :bannerList="bannerList"></home-swiper>
    <home-recommend-view :recommendList="recommendList"></home-recommend-view>
    <feature-view></feature-view>
    <tab-control :titles="['流行','新款','精选']"
                 class="tab-control"></tab-control>
    <ul>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
      <li></li>
    </ul>
  </div>
</template>

<script>
import NavBar from 'components/common/navbar/NavBar.vue'
import TabControl from '../../components/content/tabControl/TabControl.vue'

import { getHomeMultidata, getHomeGoods } from 'network/home.js'
import HomeSwiper from './childHome/HomeSwiper.vue'
import HomeRecommendView from './childHome/HomeRecommendView.vue'
import FeatureView from './childHome/FeatureView.vue'




export default {
  components: {
    NavBar,
    TabControl,
    HomeSwiper,
    HomeRecommendView,
    FeatureView,

  },
  data () {

    return {
      bannerList: [],
      recommendList: [],
      goods: {
        'pop': { page: 0, list: [] },
        'news': { page: 0, list: [] },
        'sell': { page: 0, list: [] },
      }
    }
  },
  created () {
    //1.请求多个数据
    this.getHomeMultidata();
    //2.请求推荐商品数据
    this.getHomeGoods();
  },
  methods: {
    getHomeMultidata () {
      getHomeMultidata().then(res => {
        console.log(res);
        this.bannerList = res.data.banner.list;
        this.recommendList = res.data.recommend.list;
      })
    },
    getHomeGoods () {
      getHomeGoods('pop', 1).then(res => {
        console.log(res + '1');
      })
    }

  }
}

</script>
<style scoped>
#home {
  padding-top: 44px;
}
.home-nav {
  background-color: var(--color-tint);
  color: #fff;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1;
}
.tab-control {
  position: sticky;
  top: 44px;
  background-color: #fff;
}
</style>