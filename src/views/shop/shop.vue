<template>
  <div class="wrapper">
    <div class="search">
      <div
        class="search__back iconfont"
        @click="handleBackClick"
      >&#xe7e0;</div>
      <div class="search__content">
        <span class="search__content__icon iconfont ">&#xe6e1;</span>
        <input class="search__content__input" placeholder="请输入商品名称" />
      </div>
    </div>
    <ShopInfo :item="item" :hideBorder="true" v-show="item.imgUrl"/>
    <Content />
    <Cart />
  </div>
</template>

<script>
import ShopInfo from '../../components/shopinfo'
import { reactive, toRefs } from 'vue'
import { get } from '@/utils/request'
import { useRouter, useRoute } from 'vue-router'
import Content from './content'
import Cart from './cart'

// 获取当前商铺信息
const useShopInfoEffect = () => {
  const route = useRoute()
  const data = reactive({
    item: {}
  })
  const { item } = toRefs(data)
  const getItemData = async () => {
    const result = await get(`api/shop/${route.params.id}`)
    if (result?.errno === 0 && result?.data) {
      data.item = result.data
    }
  }
  return { item, getItemData }
}

// 点击回退逻辑
const useBackEffect = () => {
  const router = useRouter()
  const handleBackClick = () => {
    router.back()
  }
  return { handleBackClick }
}
export default {
  name: 'Shop',
  components: { ShopInfo, Content, Cart },
  // setup 里只放流程
  setup () {
    const { item, getItemData } = useShopInfoEffect()
    getItemData()
    const handleBackClick = useBackEffect()
    return { handleBackClick, item }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  padding: 0 .18rem;
}
.search {
  display: flex;
  margin: .14rem 0 .04rem 0;
  line-height: .32rem;
  &__back {
    font-size: .25rem;
    width: .3rem;
    color: #B6B6B6;
  }
  &__content {
    display: flex;
    flex: 1;
    background: #F5F5F5;
    border-radius: .16rem;
    &__icon {
      width: .44rem;
      font-size: .25rem;
      text-align: center;
      color: #B7B7B7;

    }
    &__input {
      line-height: .32rem;
      width: 100%;
      border: none;
      outline: none;
      padding-right: .2rem;
      background: none;
      font-size: .14rem;
      color: #333;

      &::placeholder {
        color: #333
      }
    }
  }
}
</style>
