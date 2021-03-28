<template>
  <div class="tab-control">
    <div class="tab-control-item"
         v-for="(item,index) in titles"
         :key="index"
         @click="changeIndex(index)">
      <span :class="{active: currentIndex===index}">{{item}}</span>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      currentIndex: 0,

    }
  },
  props: {
    titles: {
      type: Array,
      default () {
        return [];
      }
    }
  },
  methods: {
    changeIndex (index) {
      this.currentIndex = index;
    }
  }

}

</script>
<style scoped>
.tab-control {
  display: flex;
  text-align: center;
  font-size: 15px;
  height: 40px;
  line-height: 40px;
}
.tab-control-item {
  flex: 1;
}
.tab-control-item span {
  padding: 5px;
}
.active {
  color: var(--color-high-text);
  border-bottom: 3px solid var(--color-tint);
}
</style>