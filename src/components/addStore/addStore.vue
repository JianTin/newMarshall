<template>
  <div id="outer">
    <div id="mask">
      <div id="addStore">
        <div id="header">
          <p>入库</p>
          <p> × </p>
        </div>
        <div id="content">
          <div id="left">

          </div>
          <div id="right"></div>
        </div>
        <div id="footer"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style lang="stylus" scoped>
#outer
  width 100%
  height 100%
  position fixed
  left 0
  top 0
#mask
  width 100%
  height 100%
  background rgba(0, 0, 0, 0.5)
  display flex
  align-items center
  justify-content center
  #addStore
    margin-top 40px
    width 640px
    height 640px
    background white
    display flex
    flex-direction column
    #header
      width 100%
      height 60px
      display flex
      p
        &:nth-child(1)
          width 90%
        &:nth-child(2)
          width 10%
</style>
