<template>
<div>
<div class="title">热销推荐</div>
 <ul>
 <router-link tag="li"
 class="item-li item " v-for="item of list" :key='item.id'
 :to="'/detail/'+item.id"
 >
 <div>
 <img class="item-img" :src="item.imgUrl"/>
 </div>
 <div class="item-info">
 <p class="item-title">{{item.title}}</p>
 <p class="item-desc">{{item.desc}}</p>
 <button class="item-button">查看详情</button>
 </div>
 </router-link>

 </ul>
</div>
</template>
<script>
export default{
   name:'HomeRecommend',
  props:{
     list:Array
   }
}
</script>
<style lang="stylus" scoped>
 @import '~styles/mixins.styl'
  .title
    margin-top:5px
    line-height:28px
    background:#eee
    text-indent:4px
    padding-left:8px
    font-weight:bold
  .item
    height:90px
    border-bottom:1px solid #e0e0e0
  .item-li
      display:flex
  .item-img
       width:80px
       height:80px
       padding:5px
       flex:1
  .item-info
       flex:1
       padding:5px
       min-width:0
  .item-title
       line-height:20px
       margin-top:5px
       ellipsis()
  .item-desc
      line-height:20px
      color:#c7c7c7
      ellipsis()
  .item-button
     margin-top:5px
     line-height:20px
     background:#ff9300
     padding:0 5px
     border-radius:5px
     color:#FFF
     border: 1px solid #fff




</style>
