<template>
  <div class="hello">
    <div class="shop-name">商品名称: {{shop.name}}</div>
    <div class="shop-price">商品价格: {{shop.price}}</div>
    <button @click="showShopInfo()">show</button>
  </div>
</template>
<script>
import { ref } from '@vue/reactivity'
import { watchEffect } from '@vue/runtime-core'
export default {
  name: 'HelloWorld',
  props: {
    shop: Object
  },
  setup(props){
    let shop = ref({})
    shop.value = props.shop
    const showShopInfo = ()=>{
      console.log(props.shop)
      // console.log(shop.value)
    }

    // watchEffect(()=>{
    //   shop.value = props.shop
    // })

    return {
      shop,
      showShopInfo
    }

  }
}
</script>

<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
