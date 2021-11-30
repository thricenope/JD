<template>
  <div class="wrapper">
    <div class="position">
      <span class="iconfont position__icon">&#xe616;</span>
      北京理工大学
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
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/超市.png"
        />
        <p class="icons__item__desc">超市便利</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/菜市场.png"
        />
        <p class="icons__item__desc">菜市场</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/水果店.png"
        />
        <p class="icons__item__desc">水果店</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/鲜花.png"
        />
        <p class="icons__item__desc">鲜花绿植</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/医药健康.png"
        />
        <p class="icons__item__desc">医药健康</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/家居.png"
        />
        <p class="icons__item__desc">家居时尚</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/蛋糕.png"
        />
        <p class="icons__item__desc">烘焙蛋糕</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/签到.png"
        />
        <p class="icons__item__desc">签到</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/大牌免运.png"
        />
        <p class="icons__item__desc">大牌免运</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__img"
          src="http://www.dell-lee.com/imgs/vue3/红包.png"
        />
        <p class="icons__item__desc">红包套餐</p>
      </div>
    </div>
    <div class="gap"></div>
    <h3 class="nearby__title">附近店铺</h3>
    <div class="nearby">
      <div class="nearby__item">
        <img
          class="nearby__item__img"
          src="http://www.dell-lee.com/imgs/vue3/near.png"
        >
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag ">月售1万+</span>
            <span class="nearby__content__tag ">起送¥0</span>
            <span class="nearby__content__tag ">基础运费¥5</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享智商税</p>
        </div>
      </div>
    </div>
    <div class="nearby">
      <div class="nearby__item">
        <img
          class="nearby__item__img"
          src="http://www.dell-lee.com/imgs/vue3/near.png"
        >
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag ">月售1万+</span>
            <span class="nearby__content__tag ">起送¥0</span>
            <span class="nearby__content__tag ">基础运费¥5</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享智商税</p>
        </div>
      </div>
    </div>
    <div class="nearby">
      <div class="nearby__item">
        <img
          class="nearby__item__img"
          src="http://www.dell-lee.com/imgs/vue3/near.png"
        >
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag ">月售1万+</span>
            <span class="nearby__content__tag ">起送¥0</span>
            <span class="nearby__content__tag ">基础运费¥5</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享智商税</p>
        </div>
      </div>
    </div>
    <div class="nearby">
      <div class="nearby__item">
        <img
          class="nearby__item__img"
          src="http://www.dell-lee.com/imgs/vue3/near.png"
        >
        <div class="nearby__content">
          <div class="nearby__content__title">沃尔玛</div>
          <div class="nearby__content__tags">
            <span class="nearby__content__tag ">月售1万+</span>
            <span class="nearby__content__tag ">起送¥0</span>
            <span class="nearby__content__tag ">基础运费¥5</span>
          </div>
          <p class="nearby__content__highlight">VIP尊享智商税</p>
        </div>
      </div>
    </div>
  </div>
  <div class="docker">
    <div class="docker__item">
      <div class="iconfont">&#xe7d4;</div>
      <div class="docker__title">首页</div>
    </div>
    <div class="docker__item docker__item--active">
      <div class="iconfont">&#xe600;</div>
      <div class="docker__title">购物车</div>
    </div>
    <div class="docker__item">
      <div class="iconfont">&#xe60a;</div>
      <div class="docker__title">订单</div>
    </div>
    <div class="docker__item">
      <div class="iconfont">&#xe78b;</div>
      <div class="docker__title">我的</div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Home'
}
</script>

<style lang="scss">
// BEM 的CSS 命名： block__element--modifier
@import "../../style/variables";
@import "../../style/mixins";
@import "../../style/mixins";

.wrapper {
  overflow-y: auto;
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem .1rem .18rem;
  color: $content-fontcolor;;
}

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

.docker {
  display: flex;
  box-sizing: border-box;
  position: absolute;
  padding: 0 .18rem;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 0.49rem;
  border-top: .01rem solid $content-bgcolor;
  color: $content-fontcolor;

  &__item {
    flex: 1;
    text-align: center;

    .iconfont {
      margin: .07rem 0 .02rem 0;
      font-size: .18rem;
    }

    &--active {
      color: #1FA4FC;
    }
  }

  &__title {
    font-size: .2rem;
    transform: scale(.5, .5);
    transform-origin: center top;
  }
}
</style>
