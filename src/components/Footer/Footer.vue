<template>
  <div class="footerbar">
    <div class="footerbar-in">
      <p class="links">
        <a href="#">关于</a>
        <a href="#">商务</a>
        <a href="#">联系</a>
        <a href="#">帮助</a>
        <a href="#">友情链接</a>
      </p>
      <p class="cr">作品著作权归会员所有&nbsp;©&nbsp;2006-2018&nbsp;Gtn9.com&nbsp;闽ICP备16006901号-2</p>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Footer',

}
</script>
<style lang='stylus' rel='stylesheet/stylus'>
.footerbar
  // 暂时这样
  position fixed
  bottom 0
  height 50px
  background #000
  width 100%
  z-index 9999
  left 0
  margin-left 0
  .footerbar-in 
    width 1180px
    max-width 1399px
    display flex
    justify-content space-around
  p
    line-height 50px
    &.links
      &>a
        color #888
        margin-right 30px
        font-size 14px
        &:hover
          color #fff
    &.cr
      color #666
      font-size 15px
</style>
