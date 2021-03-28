<template>
   <div class="tab-bar">
   <slot></slot>
   </div>
</template>

<script>
export default {
components:{

}
}
</script>

<style>
            .tab-bar {
             display: flex;
             background-color: #f6f6f6;
             position: fixed;
             left: 0;
             right: 0;
             bottom: 0;
             box-shadow: 0px -3px 1px rgba(0,0,0,.1);
           }
          
          
</style>