<template>
  <div id="app">
    <leftNav></leftNav>
    <div class="main">
        <router-view/>
    </div>
  </div>
</template>

<script>
import leftNav from '@/components/common/leftNav'
export default {
  name: 'App',
  components: {
    leftNav
  }
}
</script>

<style lang="stylus">
  .main
    float:right
    width:95%
    background-color:#eff2f7
    height:100%
    overflow:hidden
</style>
