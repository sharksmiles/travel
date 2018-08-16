<template>
<div>
<div class="banner" @click="handleBannerClick">
<img class="banner-img" :src="bannerImg"/>
<div class="banner-info">
<div class="banner-tittle">
{{this.sightName}}
</div>
<div class="banner-number">
<span class="iconfont banner-icon">&#xe692;</span>
{{this.gallaryImgs.length}}
</div>
</div>
</div>
<fade-animation>
<common-gallary :imgs="gallaryImgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
</fade-animation>
</div>
</template>
<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default{
  name:'DetailBanner',
  props:{
   sightName:String,
   bannerImg:String,
   gallaryImgs:Array
  },
  components:{
  CommonGallary,
  FadeAnimation
  },
  data (){
  return{
    showGallary:false

  }
  },
  methods:{
  handleBannerClick(){
   this.showGallary=true
  },
  handleGallaryClose(){
  this.showGallary=false
  }
  }


}
</script>
<style lang="stylus" scoped>

.banner
  position: relative
  overflow:hidden
  height:0
  padding-bottom:45%
  .banner-img
    width:100%
  .banner-info
     display: flex
     position: absolute
     left: 0
     right: 0
     bottom: 0
     line-height: 30px
     color: #fff
   .banner-tittle
     flex: 1
     font-size: 16px
     padding: 0 10px
   .banner-number
     height: 15px
     line-height: 15px
     margin-top: 7px
     padding: 0 20px
     border-radius: 10px
     background: rgba(0, 0, 0, .8)
     font-size: 14px
     .banner-icon
      font-size: 18px





</style>
