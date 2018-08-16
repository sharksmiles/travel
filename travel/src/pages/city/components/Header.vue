<template>
<div class="header">
  城市选择
  <router-link to="/">
  <div class="iconfont header-back">&#xe624;</div>
  </router-link>
</div>
</template>
<script>
export default{
  name:'CityHeader'
}
</script>
<style lang="stylus" scoped>
@import '~styles/varible.styl'
   .header
    position:relation
    height:35px
    text-align:center
    color:#fff
    background-color:$bgColor
    line-height:35px
    font-size:14px
  .header-back
    position:absolute
    top:0
    left:0
    width:17px
    text-align:center
    font-size:16px
    padding-left:7px
    color:#fff
</style>
