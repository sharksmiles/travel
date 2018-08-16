<template>
<div class="header">
<div class="header-left">
<div class="iconfont">&#xe624;</div>
</div>
<div class="header-input">
<span class="iconfont">&#xe632;</span>
输入城市/景点/游玩主题
</div>
<router-link to='/city'>
<div class="header-right">
{{this.$store.state.city}}
<span class="iconfont arrow-icon">&#xe64a;</span>
</div>
</router-link>
</div>
</template>
<script>

export default{
   name:'HomeHeader',

}
</script>
<style lang="stylus" scoped>
  @import '~styles/varible.styl'
  .header
    display: flex
    background-color:$bgColor
    color:#fff
    height:40px
    padding-left:10px
  .header-left
     flex: 1
     padding-right:15px
     line-height:36px
     padding-top:3px
  .header-input
    flex: 9
    height:25px
    margin-top: 7px
    background:#fff
    border-radius: 2px
    line-height:25px
    color:#ccc
    padding-left:5px
  .header-right
    float: right
    text-align:center
    line-height:36px
    padding-top:3px
    color:#fff
    margin-right:10px
    margin-left:15px
  .arrow-icon
    font-size:14px
</style>
