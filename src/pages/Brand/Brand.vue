<template>
  <div class="conter">
    <div class="nav">
      <div class="border"></div>
      <ul class="nav_List">
        <li class="nav-Item"
            :class="{active: type===1}"
            @click="mouse(1)">
          全部推荐
        </li>
        <li class="nav-Item"
            :class="{active: type===2}"
            @click="mouse(2)">
          最新发布
        </li>
        <li class="nav-Item "
            :class="{active: type===3}"
            @click="mouse(3)">
          上升最快
        </li>
      </ul>
    </div>
    <!--nav 下面的广告 -->
    <div class="conter_mid">
      <div class="conter_box">
        <div class="box_item">
          <img src="https://img2.gtn9.com/FvT9LEQiSjzvkhTzns6rKf0LuAgu?imageView2/1/w/280/h/220/q/100"
               alt="">
        </div>
        <div class="box_item">
          <img src='https://img2.gtn9.com/FlZra_TGkIESrCCuJx2zb89MyJvx?imageView2/1/w/280/h/220/q/100'
               alt="">
        </div>
        <div class="box_item">
          <img src="https://img2.gtn9.com/FrR0M0BCO0G6CCzoVLOXPrxwcRug?imageView2/1/w/280/h/220/q/100"
               alt="">
        </div>
        <div class="box_item">
          <img src="https://img2.gtn9.com/FvT9LEQiSjzvkhTzns6rKf0LuAgu?imageView2/1/w/280/h/220/q/100"
               alt="">
        </div>
        <div class="box_item">
          <img src="https://img2.gtn9.com/Fsbw7lOpQJSL-OzCn500o8KvDZ8t?imageView2/1/w/280/h/220/q/100"
               alt="">
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data () {
    return {
      left: 0,
      type: 1
    }
  },
  name: 'Brand',
  methods: {
    mouse (type) {
      this.type = type
      console.log(this.type)
    },
    // move (type) {
    //   this.type = type
    //   console.log(type)
    // }
  }
}
</script>
<style lang="stylus" rel="stylesheet/stylus">
.conter
  width 100%
  height 100%
  .nav
    width 100%
    position relative
    border-bottom 1px solid #ccc
    .border
      position absolute
      left 403px
      background-color #000
      z-index 99
      bottom 0
      width 90px
      height 5px
    .nav_List
      display flex
      width 1180px
      height 70px
      line-height 70px
      justify-content center
      margin 0 auto
      text-align center
      .nav-Item
        142px
        70px
        font-size 18px
        margin 0 20px
        padding 0 15px
        color #ccc
      li:hover
        color #000
      .active
        color #000
  .conter_mid
    width 100%
    .conter_box
      width 1200px
      margin 0 auto
      display flex
      flex-wrap wrap
      .box_item
        margin 30px 10px 5px
</style>