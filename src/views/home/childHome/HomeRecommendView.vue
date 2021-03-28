<template>
  <div class="recommend">
      <div v-for="(item,index) in recommendList" :key="index" class="recommend-item">
          <a :href="item.link">
              <img :src="item.image" alt="">
             <div> {{item.title}}</div>
          </a>
      </div>
  </div>
</template>

<script>
export default {
  props:{
      recommendList:{
          type:Array,
         default(){
             return [];
         }
      }
  }
}

</script>
<style scoped>
.recommend {
    display: flex;
    text-align: center;
    font-size: 12px;
    padding: 10px 0 20px;
    border-bottom:8px solid #eee;
}
.recommend-item{
    flex: 1;
}
.recommend-item img {
    width: 70px;
}

</style>