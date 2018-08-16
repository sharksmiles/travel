<template>
<div class="container" @click="handleGallaryClick">
<div class="wrapper">
<swiper :options="swiperOptions">
    <swiper-slide
    v-for="(item,index) in imgs" :key="index">
    <img  class="gallary-img" :src="item"/>
    </swiper-slide>
  </swiper>
</div>
</div>
</template>
<script>

export default{
  name:'CommonGallary',
  props:{
     imgs:{
  type:Array,
  default(){
   return []
  }
  }
  },
  methods:{
  handleGallaryClick(){
    this.$emit('close')
  }
  },
  data () {
    return {
      swiperOptions: {

        paginationType: 'fraction',
        observeParents: true,
        observer: true
      }
    }
  },


}
</script>
<style lang="stylus" scoped>

  .container
     display:flex
     flex-direction:column
     justify-content:center
     z-index:99
     position: fixed
     left:0
     right:0
     top: 0
     bottom:0
     background:#000
     .wrapper
       height:0
       width:100%
       padding-bottom:100%
       .gallary-img
         width:100%


</style>
