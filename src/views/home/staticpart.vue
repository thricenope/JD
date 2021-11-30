<template>
  <div class="position">
    <span class="iconfont position__icon">&#xe616;</span>
    北京理工大学国防科技园10号楼10单元1010门今天没人在家
    <span class="iconfont position__notice">&#xe601;</span>
  </div>
  <div class="search">
    <span class="iconfont">&#xe6e1;</span>
    <span class="search__text">窝窝头一块钱四个</span>
  </div>
  <div class="banner">
    <img class="banner__img" src="http://www.dell-lee.com/imgs/vue3/banner.jpg"/>
  </div>
  <div class="icons">
    <div
      class="icons__item"
      v-for="item in iconList"
      :key="item.desc"
    >
      <img
        class="icons__item__img"
        :src="`http://www.dell-lee.com/imgs/vue3/${item.imgName}.png`"
      />
      <p class="icons__item__desc">{{ item.desc }}</p>
    </div>
  </div>
  <div class="gap"></div>
</template>

<script>
export default {
  name: 'StaticPart',
  setup () {
    const iconList = [
      { imgName: '超市', desc: '超市便利' },
      { imgName: '菜市场', desc: '菜市场' },
      { imgName: '水果店', desc: '水果店' },
      { imgName: '鲜花', desc: '鲜花绿植' },
      { imgName: '医药健康', desc: '医药健康' },
      { imgName: '蛋糕', desc: '烘焙蛋糕' },
      { imgName: '家居', desc: '家居时尚' },
      { imgName: '签到', desc: '签到' },
      { imgName: '大牌免运', desc: '大牌免运' },
      { imgName: '红包', desc: '红包套餐' }
    ]
    return { iconList }
  }
}
</script>

<style lang="scss" scoped>
@import "../../style/variables";
@import "../../style/mixins";

.position {
  position: relative;
  padding: .16rem .24rem .16rem 0;
  line-height: .22rem;
  font-size: .16rem;
  color: $content-fontcolor;
  @include ellipsis;

  .position__icon {
    position: relative;
    top: .01rem;
    font-size: .2rem;
  }

  .position__notice {
    position: absolute;
    top: .17rem;
    right: 0;
    font-size: .2rem;
  }
}

.search {
  margin-bottom: .12rem;
  line-height: .32rem;
  background: #F5F5F5;
  color: #B7B7B7;
  border-radius: .16rem;

  .iconfont {
    position: relative;
    top: .03rem;
    display: inline-block;
    padding: 0 .12rem 0 .16rem;
    font-size: .2rem;
  }

  &__text {
    display: inline-block;
    font-size: .14rem;
  }
}

.banner {
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;

  &__img {
    width: 100%
  }
}

.icons {
  margin-top: .16rem;
  padding-bottom: .16rem;
  display: flex;
  flex-wrap: wrap;

  &__item {
    width: 20%;

    &__img {
      display: block;
      width: .4rem;
      height: .4rem;
      margin: 0 auto;
    }

    &__desc {
      margin: .06rem 0 .16rem 0;
      text-align: center;
      color: $content-fontcolor;
    }
  }
}

.gap {
  margin: 0 .18rem;
  height: .1rem;
  background: $content-bgcolor;
}
</style>
