<template>
  
       <div class="tab-bar-item" @click="itemClick">
           <slot name="item-icon" v-if="!isActive"></slot>
           <slot name="item-icon_active" v-else></slot>
           <div :style="activeStyle" >
                 <slot name="item-font"></slot>   <!--组件标签中的内容会把插槽slot替换掉 -->
           </div>
            
         </div>
 
</template>

<script>
export default {
  props:{
    path:String,
    activeColor:{
      type:String,
      default:'red'
    }
  },
data(){
    return {
        
    }
},
methods:{
  itemClick(){
   
    this.$router.push(this.path)
  },
},
computed:{
  isActive(){
  return this.$route.path.indexOf(this.path) !=-1;             
  },
  activeStyle(){
    return this.isActive? {color:this.activeColor} : {};
  }
}
}

</script>
<style scoped>
    .tab-bar-item{
             flex: 1;
             text-align: center;
             height: 49px;
             font-size: 14px;
           
            
           }
     .tab-bar-item img {
               width: 24px;
               height: 24px;
               vertical-align: middle;
                 margin-top: 3px;
                 margin-bottom: 2px; 
           }
     
</style>