<template>
  <div class="home">
    <div class="shop-list">
      <div class="item" v-for="(item,index) in shopList" :key="index" @click="showShowInfo(item)">
        <div class="name">{{item.name}}</div>
        <div class="price">{{item.price}}</div>
      </div>
    </div>

    <HelloWorld :shop="showItem" v-if="isShowShowInfo"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'
import { reactive,ref } from '@vue/reactivity'

export default {
  name: 'HomeView',
  components: {
    HelloWorld
  },
  setup(){
    let isShowShowInfo = ref(false)
    let shopList = reactive([
      {
        name:"小米11",
        price:3000
      },
      {
        name:"苹果11",
        price:6000
      },
      {
        name:"华为meta50",
        price:10000
      }
    ])
    let showItem = ref({})
    const showShowInfo = (item)=>{
      showItem.value = item
      isShowShowInfo.value = true
    }




  return {
    shopList,
    showItem,
    showShowInfo,
    isShowShowInfo
  }


  }
}
</script>

<style scoped lang="scss">
.shop-list{
  width: 100%;
  .item{
    display: flex;
    width: 150px;
    justify-content: space-between;
    align-items: center;
    cursor: pointer;
    margin-bottom: 20px;
  }
}
</style>
