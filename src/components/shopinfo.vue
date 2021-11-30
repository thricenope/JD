<template>
    <div class="shop">
      <img class="shop__img" :src="item.imgUrl">
      <div class="shop__content">
        <div class="shop__content__title">{{ item.name }}</div>
        <div class="shop__content__tags">
          <span class="shop__content__tag ">月售: {{ item.sales }}</span>
          <span class="shop__content__tag ">起送: {{ expressLimit }}</span>
          <span class="shop__content__tag ">基础运费: {{ expressPrice  }}</span>
        </div>
        <p class="shop__content__highlight">{{ item.slogan }}</p>
      </div>
    </div>
</template>

<script>
export default {
  name: 'ShopInfo',
  props: ['item']
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

.shop {
  padding-top: .12rem;
  display: flex;

  &__img {
    margin-right: .16rem;
    width: .56rem;
    height: .56rem;
  }
  &__content {
    padding-bottom: .12rem;
    border-bottom: .01rem solid $content-bgcolor;
    flex: 1;

    &__title {
      line-height: .16rem;
      font-size: .22rem;
      color: $content-fontcolor;
    }

    &__tags {
      margin-top: .08rem;
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
    }

    &__tag {
      margin-right: .16rem;
    }

    &__highlight {
      margin: .08rem 0 0 0;
      line-height: .18rem;
      font-size: .13rem;
      color: #E93B3B;
    }
}
}

</style>
