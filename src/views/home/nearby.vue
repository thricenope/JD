<template>
  <h3 class="nearby__title">附近店铺</h3>
  <div class="nearby">
    <div
      class="nearby__item"
      v-for="item in nearbyList"
      :key="item.id"
    >
      <img class="nearby__item__img" :src="item.imgUrl">
      <div class="nearby__content">
        <div class="nearby__content__title">{{ item.title }}</div>
        <div class="nearby__content__tags">
          <span
            class="nearby__content__tag "
            v-for="(innerItem,innerIndex) in item.tags"
            :key="innerIndex"
          >{{ innerItem }}</span>
        </div>
        <p class="nearby__content__highlight">{{ item.desc }}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nearby',
  setup () {
    const nearbyList = [
      {
        id: 1,
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        title: '沃尔玛',
        tags: ['月售1万+', '起送¥0', '基础运费¥5'],
        desc: 'VIP尊享智商税'
      },
      {
        id: 2,
        title: '沃尔玛',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        tags: ['月售1万+', '起送¥0', '基础运费¥5'],
        desc: 'VIP尊享智商税'
      },
      {
        id: 2,
        title: '沃尔玛',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        tags: ['月售1万+', '起送¥0', '基础运费¥5'],
        desc: 'VIP尊享智商税'
      },
      {
        id: 2,
        title: '沃尔玛',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        tags: ['月售1万+', '起送¥0', '基础运费¥5'],
        desc: 'VIP尊享智商税'
      },
      {
        id: 2,
        title: '沃尔玛',
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/near.png',
        tags: ['月售1万+', '起送¥0', '基础运费¥5'],
        desc: 'VIP尊享智商税'
      }
    ]
    return {
      nearbyList
    }
  }
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

  &__item {
    padding-top: .12rem;
    display: flex;

    &__img {
      margin-right: .16rem;
      width: .56rem;
      height: .56rem;
    }
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
