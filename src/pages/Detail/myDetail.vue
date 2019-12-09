<template>
  <div>
    <div id="outer">
      <header>
        <img src="./image/ia_400000093.jpg" />
        <div id="active">
          <img src="./image/ia_400000009.jpg" alt="" />
          <span> Lv 2</span>
          <p id="name">边缘浪子</p>
          <p>不详</p>
        </div>
        <ul id="content">
          <li>
            <span>人气</span>
            <p>5.1亿</p>
          </li>
          <li>
            <span>人气</span>
            <p>5.1亿</p>
          </li>
          <li>
            <span>人气</span>
            <p>5.1亿</p>
          </li>
          <li>
            <span>人气</span>
            <p>5.1亿</p>
          </li>
        </ul>
        <div id="linked">
          <button>关注</button>
          <button>私信</button>
        </div>
      </header>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="stylus" scoped>
#outer
  width 1200px
  margin 0 auto
  header
    &>img
      margin-top 50px
    #active
      width 120px
      height 115px
      border-radius 50%
      border-left solid 6px rgb(0,128,255)
      padding-left 2px
      position relative
      margin 0 auto
      transform translateY(-70%) translateX(-10px)
      background white
      img
        width 100%
        height 100%
        border-radius 50%
      span
        position absolute
        bottom 0
        left 50%
        transform translateX(-50%) translateY(50%)
        background rgb(0,128,255)
        width 45px
        height 20px
        border-radius 10px
        text-align center
        line-height 20px
        color  white
        font-size 12px
      #name
        margin-top 25px
        margin-bottom 10px
        text-align center
        color: #000;
        font-size: 18px;
      p
        text-align center
        color #B8B8B8
    #content
      display flex
      width 460px
      justify-content space-around
      margin 40px auto
      li
        width 110px
        height 30px
        border-right 1px black solid
        display flex
        flex-direction  column
        justify-content center
        align-items center
        &:nth-child(4)
          border 0
        span
          text-align: center;
          font-size: 12px;
          color: #999
    #linked
      width 200px
      height 40px
      display flex
      justify-content space-around
      margin 0 auto
      button
        all  unset
        width: 80px;
        height: 36px;
        font-size: 14px;
        color: #fff;
        line-height: 36px;
        background: #000;
        border-radius: 3px;
        float: left;
        cursor: pointer;
        text-align: center;
</style>
