<template>
<div>
<div class="title">周末去哪儿</div>
 <ul>
 <li class="item-li item border-bottom" v-for="(item,id) of list" :key='item.id'>
 <div class="item-img-wrapper">
 <img class="item-img" :src="item.imgUrl"/>
 </div>
 <div class="item-info">
 <p class="item-title">{{item.title}}</p>
 <p class="item-desc">{{item.desc}}</p>
 </div>
 </li>
 </ul>
</div>
</template>
<script>
export default{
   name:'HomeWeekend',
   props:{
   list:Array
   }
}
</script>
<style lang="stylus" scoped>
 @import '~styles/mixins.styl'
  .title

    line-height:28px
    background:#eee
    text-indent:4px
    padding-left:8px
    font-weight:bold
  .item-img-wrapper
    height:0
    padding-bottom:37%
    margin-bottom:10px
  .item-img
       width:100%
  .item-info
       min-width:0
       margin-left:10px
       margin:18px 10px 10px
       font-size:12px
  .item-title
       ellipsis()


  .item-desc
      color:#c7c7c7

      ellipsis()

</style>
