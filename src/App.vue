<template>
  <div id="app">
    <m-header></m-header>
    <!--需要缓冲的组件-->
    <keep-alive>
      <router-view v-if="$route.meta.keepAlive"></router-view>
    </keep-alive>

    <!--不需要缓冲的组件-->
    <router-view v-if="!$route.meta.keepAlive"></router-view>

    <tab></tab>
  </div>
</template>

<script type="text/ecmascript-6">

  import MHeader from '@/components/m-header/m-header'
  import Tab from '@/components/tab/tab'

  export default {
    components: {
      MHeader,
      Tab
    },
  }

</script>

<style scoped lang="stylus" ref="stylesheet/stylus">
  @import "~common/stylus/variable"

  #app
    color: $color-theme
</style>
