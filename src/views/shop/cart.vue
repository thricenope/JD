<template>
  <div class="cart">
    <div class="check">
      <div class="check__icon">
        <img
          src="http://www.dell-lee.com/imgs/vue3/basket.png"
          class="check__icon__img "
        />
        <div class="check__icon__tag">{{ total }}</div>
      </div>
      <div class="check__info">
        总计: <span class="check__info__price">&yen; {{ price  }}</span>
      </div>
      <div class="check__btn">去结算</div>
    </div>
  </div>
</template>

<script>
import { computed } from 'vue'
import { useStore } from 'vuex'
import { useRoute } from 'vue-router'

const useCartEffect = () => {
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
        count += (product.count * product.price)
      }
    }
    return count.toFixed(2)
  })
  return { total, price }
}

export default {
  name: 'Cart',
  setup () {
    const { total, price } = useCartEffect()
    return { total, price }
  }
}
</script>

<style lang="scss" scoped>

.cart {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  height: .5rem;
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
