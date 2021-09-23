<template>
  <div class="tab-control">
    <div v-for="(item,index) in title"
         class="tab-control-item"
         :class="{active:currentIndex == index}"
         @click="itemClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props:{
    title:{
      type:Array,
      default(){
        return[]
      }
    }
  },
  data(){
    return{
      currentIndex:0
    }
  },
  methods:{
    itemClick(index){
      this.currentIndex=index
    }
  }
}
</script>

<style scoped>
.tab-control{
  display: flex;
  text-align: center;
  height: 40px;
  line-height: 40px;
  font-size: 15px;
}
.tab-control-item{
  flex: 1;
}
.tab-control-item span{
  padding-bottom: 5px;
}
.active{
  color:var(--color-high-text);
}
.active span{

  border-bottom: 3px solid var(--color-high-text);
}
</style>
