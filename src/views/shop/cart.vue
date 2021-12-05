<template>
  <div class="cart">
    <div class="product">
      <div class="product__header">
        全选
      </div>
      <template v-for="item in productList" :key="item._id">
        <div class="product__item" v-if="item.count > 0 ">
          <div
            class="product__item__checked iconfont"
            v-html="item.check ? '&#xe70f;': '&#xe66c;'"
            @click="() => { changeCartChecked(shopId, item._id) }"
          />
          <img
            class="product__item__img"
            :src=item.imgUrl
            v-show="item.imgUrl"
          >
          <div class="product__item__detail">
            <h4 class="product__item__title">{{ item.name }}</h4>
            <p class="product__item__price">
              <span class="product__item__yen">&yen;</span>{{ item.price }}
              <span class="product__item__origin">&yen;{{ item.oldPrice }}</span>
            </p>
          </div>
          <div class="product__number">
            <span
              class="product__number__minus"
              @click="() => { changeCartItemInfo( shopId, item._id, item, -1) }"
            >-</span>
            {{ item.count || 0 }}
            <span
              class="product__number__plus"
              @click="() => { changeCartItemInfo( shopId, item._id, item, 1) }"
            >+</span>
          </div>
        </div>
      </template>
    </div>
    <div class="check">
      <div class="check__icon">
        <img
          src="http://www.dell-lee.com/imgs/vue3/basket.png"
          class="check__icon__img "
        />
        <div class="check__icon__tag">{{ total }}</div>
      </div>
      <div class="check__info">
        总计: <span class="check__info__price">&yen; {{ price }}</span>
      </div>
      <div class="check__btn">去结算</div>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
import { useStore } from 'vuex'
import { useRoute } from 'vue-router'
import { useCommonCartEffect } from '@/views/shop/commonCartEffect'

const useCartEffect = () => {
  const { changeCartItemInfo } = useCommonCartEffect()
  const store = useStore()
  const route = useRoute()
  const shopId = route.params.id
  const cartList = store.state.cartList

  const total = computed(() => {
    const productList = cartList[shopId]
    let count = 0
    if (productList) {
      for (const i in productList) {
        const product = productList[i]
        count += product.count
      }
    }
    return count
  })

  // 获取购物车信息逻辑
  const price = computed(() => {
    const productList = cartList[shopId]
    let count = 0
    if (productList) {
      for (const i in productList) {
        const product = productList[i]
        if (product.check) {
          count += (product.count * product.price)
        }
      }
    }
    return count.toFixed(2)
  })

  const productList = computed(() => {
    const productList = cartList[shopId] || []
    return productList
  })

  const changeCartChecked = (shopId, productId) => {
    store.commit('changeCartChecked', { shopId, productId })
    return { changeCartChecked }
  }
  return { total, price, productList, changeCartItemInfo, changeCartChecked }
}

export default {
  name: 'Cart',
  setup () {
    const route = useRoute()
    const shopId = route.params.id
    const { total, price, productList, changeCartItemInfo, changeCartChecked } = useCartEffect()
    return { shopId, total, price, productList, changeCartItemInfo, changeCartChecked }
  }
}
</script>

<style lang="scss" scoped>
@import "../../style/mixins";

.cart {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: .5rem;
}

.product {
  overflow-y: scroll;
  flex: 1;
  background-color: #FFF;
  &__header {
    height: .52rem;
    border-bottom:1px solid #F1F1F1;
  }
  &__item {
    position: relative;
    display: flex;
    padding: .12rem 0;
    margin: 0 .16rem;
    border-bottom: .01rem solid #F1F1F1;

    &__detail {
      overflow: hidden;
    }
    &__checked {
      line-height: .5rem;
      margin-right: .2rem;
      color: #0091FF;
      font-size: .2rem;
    }
    &__img {
      width: .46rem;
      height: .46rem;
      margin-right: .16rem;
    }

    &__title {
      margin: 0;
      line-height: .2rem;
      font-size: .14rem;
      color: #333;
      @include ellipsis
    }

    &__price {
      margin-top: .06rem;
      line-height: .2rem;
      font-size: .14rem;
      color: #E93B3B;
    }

    &__yen {
      font-size: .12rem;
    }

    &__origin {
      margin-left: .06rem;
      line-height: .2rem;
      font-size: .12rem;
      color: #999;
      text-decoration: line-through;
    }

    .product__number {
      position: absolute;
      right: 0;
      bottom: .12rem;

      &__minus,
      &__plus {
        display: inline-block;
        width: .2rem;
        height: .2rem;
        line-height: .16rem;
        border-radius: 50%;
        font-size: .2rem;
        text-align: center;
      }

      &__minus {
        border: .01rem solid #666;
        color: #666;
        margin-right: .05rem;
      }

      &__plus {
        background: #0091FF;
        color: #FFF;
        margin-left: .05rem;
      }
    }
  }
}

.check {
  display: flex;
  line-height: .5rem;
  border-top: .01rem solid #F1F1F1;

  &__icon {
    position: relative;
    width: .84rem;

    &__img {
      display: block;
      margin: .12rem auto;
      height: .28rem;
      width: .26rem;
    }

    &__tag {
      position: absolute;
      left: .46rem;
      right: .2rem;
      top: .03rem;
      padding: 0 .04rem;
      min-width: .2rem;
      height: .2rem;
      line-height: .2rem;
      font-size: .12rem;
      text-align: center;
      background-color: #E93B3B;
      border-radius: .1rem;
      color: #FFF;
      transform: scale(.7);
      transform-origin: left center;
    }
  }

  &__info {
    flex: 1;
    color: #333333;
    font-size: .12rem;

    &__price {
      color: #E93B3B;
      font-size: .18rem;
    }
  }

  &__btn {
    width: .98rem;
    line-height: .5rem;
    color: #FFF;
    font-size: .14rem;
    text-align: center;
    background-color: #4FB0F9;
  }
}
</style>
