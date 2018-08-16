<template>
<div class="list" ref="wrapper">
<div>
    <div class="area">
    <div class="title border-topbottom">当前城市</div>
    <div class="button-list">
    <div class="button-wrapper">
    <div class="button">{{this.$store.state.city}}</div>
    </div>
    </div>
    </div>
    <div class="area">
    <div class="title border-topbottom">热门城市</div>
    <div class="button-list" >
    <div class="button-wrapper" v-for="item of hot"
    :key="item.id"
    @click="handleCityClick(item.name)">
    <div class="button">{{item.name}}</div>
    </div>
    </div>
    </div>
    <div class="area" v-for="(item,key) of cities" :key="key":ref="key" >
   <div class="title border-topbottom">{{key}}</div>
   <div class="item-list  border-topbottom">
    <div  v-for="innerItem of item" @click="handleCityClick(innerItem.name)"
    :key="innerItem.id" class="item border-topbottom">{{innerItem.name}}</div>

</div>
 </div>
  </div>
</div>
</template>
<script>
import Bscroll from 'better-scroll'
export default{
  name:'CityList',
  props:{
  hot: Array,
  cities:Object,
  letter:String
  },
  methods:{
  handleCityClick(city){
  this.$store.commit('changeCity',city)
  this.$router.push('/')
  }
  },
  watch:{
  letter(){
  if(this.letter){
    const element=this.$refs[this.letter][0]
   this.scroll.scrollToElement(element)
  }

  }
  },
 mounted(){
  this.scroll=new Bscroll(this.$refs.wrapper)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/varible.styl'
    .border-topbottom
       &:before
         border-color:#CCC
       &:after
         border-color:#CCC
   .list
    overflow:hidden
    position:absolute
    top:70px
    left:0
    right:0
    bottom:0
    .title
      line-height:25px
      background:#eee
      padding-left:10px
      color:#666
      font-size:14px
    .button-list
       padding:5px
       overflow:hidden
       padding:5px 30px 5px 5px
      .button-wrapper
       float:left
       width:33%
      .button
        margin:5px
        text-align:center
        padding:2px 0
        border:1px solid #ccc
        border-radius: 3px
    .item-list
      .item
        line-height:30px
        color:#666
        padding-left:10px







</style>
