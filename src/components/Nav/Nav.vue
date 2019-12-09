<template>
  <div class="center_nav_wrapper">
    <!-- 导航条的图 -->
    <div class="navImg">
      <img src="../../assets/images/nav.png"
           alt="nav">
    </div>
    <!-- 导航条 -->
    <div @mouseenter="isShow1=!isShow1"
         class="center_nav">
      <b ref="line"
         id="border"
         style="left: 314px; display: block;"></b>
      <div @mouseenter="turnLine"
           class="index_btn">
        <a>全部活动<b class="smallPoint"></b></a>
        <ul class="sub-nav-list"
            v-show="isShow1">
          <li class="sub-nav-item"><a href="#">全部活动</a></li>
          <li class="sub-nav-item"><a href="#">线上活动</a></li>
          <li class="sub-nav-item"><a href="#">线下活动</a></li>
        </ul>
      </div>
      <ul ref="navUl"
          class="activeNav">
        <li v-for="(arr,index) in array"
            :key="index"
            class="navItem"><a href="#">{{arr}}</a></li>
      </ul>
      <div @mouseenter="isShow2=!isShow2" class="index_btn2">
        <a>全部<b class="smallPoint"></b></a>
        <ul class="sub-nav-list2"
            v-show="isShow2">
          <li class="sub-nav-item"><a href="#">全部</a></li>
          <li><a href="#">进行中</a></li>
          <li><a href="#">已结束</a></li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Nav',
  data () {
    return {
      isShow1: false, // 下拉单默认不显示
      isShow2: false, // 下拉单默认不显示
      array: ['课程', '大赛', '征集', '沙龙', '展览']
    }
  },
  mounted () {
    const ul = this.$refs.navUl.children
    const line = this.$refs.line
    const lis = Array.from(ul)
    lis.forEach(li => {
      line.style.width = li.offsetWidth + 'px'
      let leftFloat = line.offsetWidth
      li.onmouseenter = () => {
        line.style.left = li.getBoundingClientRect().left - leftFloat + 'px'
      }
      li.onmouseleave = () => {
        line.style.left = 314 + 'px'
      }
    })
  },
  methods: {
    turnLine () {
      const line = this.$refs.line
      line.style.left = 314 + 'px'
    }
  }
}
</script>
<style lang='stylus' rel='stylesheet/stylus'>
.center_nav_wrapper
  width 100%
  .navImg
    width 1180px
    height 280px
    margin 20px auto
    img
      width 100%
      height 100%
  .center_nav
    width 1180px
    height 70px
    margin 0 auto
    position relative
    display flex
    justify-content center
    align-items center
    #border
      width 86px
      height 3px
      position absolute
      bottom -1px
      z-index 10
      background-color #000
      transition all 0.2s linear
    .activeNav
      display flex
      justify-content center
      align-items center
      .navItem
        width 86px
        height 70px
        line-height 70px
        font-size 18px
        text-align center
        &:hover a
          color #000
        a
          color #999
    .index_btn
      width 122px
      position relative
      a
        font-size 18px
        color #000
      .smallPoint
        display inline-block
        margin-left 6px
        border 5px solid transparent
        border-top 5px solid #000
      .sub-nav-list
        position absolute
        left -20px
        top 30px
        width 110px
        border-radius 3px
        border 1px solid #dcdcdc
        .sub-nav-item
          width 100%
          height 40px
          line-height 40px
          text-align center
          &:hover
            background-color #000
            a
              color #fff
          &>a
            font-size 14px
            color #000
    .index_btn2
      width 70px
      height 70px
      font-size 12px
      position absolute
      top 30px
      right -20px
      &>a
        font-size 12px
        color #666
      .smallWord
        margin-left -8px
      .smallPoint
        display inline-block
        border 5px solid transparent
        border-top 5px solid #000
        margin-left 15px
      &.current
        background-color #000
        a
          color #fff
      .sub-nav-list2
        display flex
        flex-direction column
        border-radius 3px
        border 1px solid #dcdcdc
        width 88px
        margin-top 20px 
        margin-left -30px
        li
          width 100%
          height 40px
          line-height 40px
          text-align center
          &:hover
            background-color #000
            a
              color #fff
          &>a
            font-size 14px
            color #000
          a
            font-size 12px
            color #666
        .sub-nav-item
          margin-left -5px
          
</style>
