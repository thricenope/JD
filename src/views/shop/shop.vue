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
    <ShopInfo :item="item" :hideBorder="true"/>
  </div>
</template>

<script>
import ShopInfo from '../../components/shopinfo'
import { useRouter } from 'vue-router'

export default {
  name: 'Shop',
  components: { ShopInfo },
  setup () {
    const router = useRouter()
    const item = {
      _id: '1',
      name: '沃尔玛',
      imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
      sales: 10000,
      expressLimit: 0,
      expressPrice: 5,
      slogan: 'VIP尊享满89元减4元运费券'
    }
    const handleBackClick = () => {
      router.back()
    }
    return { item, handleBackClick }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
  padding: 0 .18rem;
}
.search {
  display: flex;
  margin: .2rem 0 .16rem 0;
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
