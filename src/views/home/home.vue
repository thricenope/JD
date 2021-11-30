<template>
  <div class="wrapper">
    <StaticPart />
    <Nearby />
  </div>
  <Docker />

</template>
<script>
import StaticPart from './staticpart'
import Nearby from './nearby'
import Docker from './docker'

export default {
  name: 'Home',
  components: { StaticPart, Nearby, Docker }
}
</script>

<style lang="scss">
// BEM 的CSS 命名： block__element--modifier
@import "../../style/variables";

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

</style>
