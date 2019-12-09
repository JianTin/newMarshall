<template>
  <!-- 头部导航 -->
  <div class="header">
    <h1 class="logo">
      <img class="logoImg"
           src="../../assets/images/logo.png"
           alt="logo">
    </h1>
    <div class="headerCenter">
      <ul class="center">
        <li><a href="#">版权登记</a><span>Beta</span></li>
        <li @mouseenter="isShow=!isShow"><a href="#">品牌</a></li>
        <li><a href="#">活动</a></li>
        <li><a href="#">观点</a></li>
        <li><a href="#">创意库</a></li>
        <li><a href="#">招聘</a></li>
        <li @mouseenter="show9=!show9">
          <a href="#">9+</a>
          <div v-show="show9" class="hide9">
            <p><a href="#">总标头商标注册</a></p>
            <p><a href="#">掘物创意商城</a></p>
          </div>
        </li>
      </ul>
      <ul class="hide" v-show="isShow">
        <li class="active"> <a href="work_list.aspx?ID=0&amp;worktype=1&amp;action=index_red">原创秀</a></li>
        <li><a href="work_list.aspx?ID=1">VIS设计</a></li>

        <li><a href="work_list.aspx?ID=425">标志设计</a></li>

        <li><a href="work_list.aspx?ID=5">字体设计</a></li>

        <li><a href="work_list.aspx?ID=4">包装设计</a></li>

        <li><a href="work_list.aspx?ID=8">交互设计</a></li>

        <li><a href="work_list.aspx?ID=11">书刊画册</a></li>

        <li><a href="work_list.aspx?ID=456">海报设计</a></li>

        <li><a href="work_list.aspx?ID=462">平面物料</a></li>

        <li><a href="work_list.aspx?ID=9">广告创意</a></li>

        <li><a href="work_list.aspx?ID=15">插画动漫</a></li>

        <li><a href="work_list.aspx?ID=10">资源库</a></li>

        <li><a href="work_list.aspx?ID=14">摄影艺术</a></li>

        <li><a href="work_list.aspx?ID=13">影视创意</a></li>

        <li><a href="work_list.aspx?ID=384">导视设计</a></li>

        <li><a href="work_list.aspx?ID=6">空间设计</a></li>

        <li><a href="work_list.aspx?ID=16">产品设计</a></li>

        <li><a href="work_list.aspx?ID=472">吉祥物</a></li>

        <li><a href="work_list.aspx?ID=12">跨界</a></li>

        <li><a href="work_list.aspx?ID=512">品牌资讯</a></li>

        <li><a href="work_list.aspx?ID=543">美妆制造局</a></li>

      </ul>
    </div>
    <div class="headerRight">
      <div class="search"></div>
      <div class="login">登录</div>
      <div class="register">注册</div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Header',
  data () {
    return {
      isShow: false,// 品牌下面的菜单默认不显示
      show9:false// 9+的显示/隐藏
    }
  }
}
</script>
<style lang='stylus' rel='stylesheet/stylus'>
.header
  width 100%
  height 70px
  background-color #000
  display flex
  align-items center
  justify-content space-around
  min-width 1200px
  .logo
    cursor pointer
  .headerCenter
    width 645px
    position relative
    .center
      width 100%
      display flex
      li
        width 90px
        height 70px
        line-height 70px
        font-size 16px
        color #999
        text-align center
        &:hover a
          color #fff
        &:hover span
          color #fff  
        a
          color #999
        &:first-child
          width 105px
          position relative
          margin-right 10px
          span
            position absolute
            right -8px
            top -2px
            font-size 12px
        &:last-child
          position relative
          .hide9
            display none
            width 160px
            background-color #000
            position absolute
            left -36px
            top 70px
            display flex
            flex-direction column
            &>p
              line-height 30px
              border-radius 3px
              margin-bottom 10px
              font-size 14px
    .hide
      display flex
      width 646px
      flex-wrap wrap
      padding 0 20px 10px 20px
      background-color #000
      columns #fff
      position absolute
      top 70px
      left 84px
      li
        width 86px
        height 30px
        line-height 30px
        border-radius 5px
        text-align center
        margin-left 18px
        margin-top 10px
        a
          font-size 14px
          color #999
        &.active
          background-color #2B9E28
          a
            color #fff
  .headerRight
    width 260px
    display flex
    color #999
    &>div:hover
      cursor pointer
      color #fff
    .search
      width 20px
      height 20px
      background url('../../assets/images/big.png')
      background-position -170px -175px
      filter brightness(.5)
      transition all .1s
      &:hover
        filter brightness(1)
    .login
      margin 0 32px
</style>
