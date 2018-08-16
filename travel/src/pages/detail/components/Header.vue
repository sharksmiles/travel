<template>
<div>
<router-link tag="div" class="header-abs" v-show="showAbs" to="/">
<div class="iconfont header-abs-back">&#xe624;</div>
</router-link>
<div class="header-fixed"  v-show="!showAbs" :style="opacityStyle">
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
景点详情
</div>
</div>
</template>
<script>

export default{
  name:'DetailHeader',
  data(){
  return {
     showAbs:true,
      opacityStyle: {
             opacity: 0
           }
  }
  },methods: {
        handleScroll () {
          const top = document.documentElement.scrollTop
          if (top > 60) {
            let opacity = top / 140
            opacity = opacity > 1 ? 1 : opacity
            this.opacityStyle = { opacity }
            this.showAbs = false
          } else {
            this.showAbs = true
          }
        }
      },
      mounted () {
        window.addEventListener('scroll', this.handleScroll)
      },
      unmounted () {
        window.removeEventListener('scroll', this.handleScroll)
      }

}
</script>
<style lang="stylus" scoped>
      .header-abs
         position: absolute
         left: 8px
         top: 10px
         width: 30px
         height: 30px
         line-height: 30px
         border-radius: 20px
         text-align: center
         background: rgba(0, 0, 0, .8)
         .header-abs-back
           color: #fff
           font-size: 16px
      .header-fixed
          z-index: 2
          position: fixed
          top: 0
          left: 0
          right: 0
          height: 30px
          line-height: 30px
          text-align: center
          color: #fff
          background: #00bcd4
          font-size: 15px
       .header-fixed-back
            position: absolute
            top: 0
            left: 0
            width: 30px
            text-align: center
            font-size: 16px
            color: #fff

</style>
