<template>
  <div>
      <tab-bar>
     <tab-bar-item  path="/home" >
       <img src="~assets/img/tabbar/home.svg" alt="" slot="item-icon">
        <img src="~assets/img/tabbar/home_active.svg" alt="" slot="item-icon_active">
            <div slot="item-font">首页</div>
     </tab-bar-item >
       <tab-bar-item path="/category" >
          <img src="~assets/img/tabbar/category.svg" alt="" slot="item-icon">
          <img src="~assets/img/tabbar/category_active.svg" alt="" slot="item-icon_active">
            <div slot="item-font">分类</div>
       </tab-bar-item>
         <tab-bar-item path="/cart">
            <img src="~assets/img/tabbar/shopcart.svg" alt="" slot="item-icon">

            <img src="~assets/img/tabbar/shopcart_active.svg" alt="" slot="item-icon_active">
            <div slot="item-font">购物车</div>
         </tab-bar-item>
           <tab-bar-item path="/profile"> 
             <img src="~assets/img/tabbar/profile.svg" alt="" slot="item-icon">
              <img src="~assets/img/tabbar/profile_active.svg" alt="" slot="item-icon_active">
            <div slot="item-font">我的</div>
           </tab-bar-item>
  </tab-bar>
  </div>
</template>

<script>
import TabBar from 'components/common/tabbar/TabBar.vue'
import TabBarItem from 'components/common/tabbar/TabBarItem.vue'
export default {
components:{
     TabBar,
   TabBarItem
}
}

</script>
<style scoped>
</style>