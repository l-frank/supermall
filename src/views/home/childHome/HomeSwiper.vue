<template>
  <div>
      <swiper>
        <swiper-item v-for="(item,index) in  bannerList" :key="index">
          <a :href="item.link">
            <img :src="item.image" alt="">
          </a>
        </swiper-item>
      </swiper>
  </div>
</template>

<script>
import {Swiper, SwiperItem} from 'components/common/swiper/index.js'
export default {
 components:{
     SwiperItem,
      Swiper
 },
 props:{
    bannerList:{
         type:Array,
         default(){
             return [];
         }
     }
 }
}

</script>
<style scoped>
</style>