<template>
  <h3 class="nearby__title">附近店铺</h3>
  <div class="nearby">
    <ShopInfo
      v-for="item in nearbyList"
      :key="item._id"
      :item="item"
    />
  </div>
</template>

<script>
import ShopInfo from '../../components/shopinfo'
import { ref } from 'vue'
import { get } from '../../../src/utils/request'
const useNearbyListEffect = () => {
  const nearbyList = ref([])
  const getNearbyList = async () => {
    const result = await get('/api/shop/hot-list')
    // console.log(result)
    if (result?.errno === 0 && result?.data?.length) {
      nearbyList.value = result.data
    }
  }
  return { nearbyList, getNearbyList }
}

export default {
  name: 'Nearby',
  setup () {
    const { nearbyList, getNearbyList } = useNearbyListEffect()
    getNearbyList()
    return { nearbyList }
  },
  components: { ShopInfo }
}
</script>

<style lang="scss" scoped>
@import "../../style/variables";

.nearby {
  &__title {
    margin: .16rem 0 .02rem 0;
    font-size: .18rem;
    color: $content-fontcolor;
    font-weight: normal;
  }
}
</style>
