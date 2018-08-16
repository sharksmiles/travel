<template>
<div class="icons">
<swiper :options="swiperOption">
<swiper-slide v-for="(page,index) of pages" :key="index">
<div class="icon" v-for="item of page" :key="item.id">
<div class="icon-img">
 <img class="icon-img-content" :src='item.imgUrl'/>
 </div>
 <p class="icon-desc">{{item.desc}}</p>
</div>
</swiper-slide>
 </swiper>
</div>
</template>

<script>
export default{
name:'HomeIcons',
props:{
  list:Array
 },
 data(){
    return{
    swiperOption:{
    autoplay:false
    }
    }
 },
computed:{
  pages(){
  const pages=[]
  this.list.forEach((item,index)=>{
  const page=Math.floor(index/8)
  if(!pages[page]){
  pages[page]=[]
  }
  pages[page].push(item)
  })
  return pages
  }
  }
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varible.styl'
 @import '~styles/mixins.styl'
 .icons >>> .swiper-container
   height:0
   padding-bottom: 40%
  .icon
    position:relative
    overflow:hidden
    float:left
    width:25%
    padding-bottom:20%


   .icon-img
    position:absolute
    top:5px
    left:0
    right:0
    bottom:15px

   .icon-img-content
    height:90%
    display:block
    margin:0px auto
  .icon-desc
    position:absolute
    left:0
    right:0
    bottom:0px
    height:22px
    line-height:22px
    color:$darkTextColor
    text-align:center

    ellipsis()






</style>
