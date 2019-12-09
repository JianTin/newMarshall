<template>
  <div>
    <Alert :isShowAlert='isShowAlert'
           :changAlertShow='changAlertShow'
           :alertText='alertText'
           ref='outerAlert' />
    <div class="content-outer">
      <ul class="content">
        <li @mouseenter="changLi"
            @mouseleave="changLi">
          <img src="./image/ia_500000003.jpg" />
          <div id="mask"
               :style="{ opacity: isOpactiyBck }"></div>
          <div>
            <p class="activityName">
              名字名字名字名字名字名字名字名字名字名字名字名字名字名字名字
            </p>
            <div class="activityTime">
              <p>2019/11/14 - 2019/12/10</p>
              <div>
                <div class="greenLeft"></div>
                <div class="greenRight">进行中</div>
              </div>
            </div>
            <p class="actvityDescribe">
              《靳埭强50+2艺术设计展》暨高端学术论坛& 靳埭强设计奖20xxxxxxx
            </p>
            <div class="Footer">
              <div class="footer-left">
                <img src="./image/ia_500000027.jpg" />
                <span>边缘浪子</span>
              </div>
              <div class="footer-right"
                   :style="{ opacity: isOpactiy }">
                <img :src="stockImg"
                     @click="addStock" />
                <button>入库</button>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>
    <AddStore />
  </div>
</template>

<script>
import AddStore from '../../components/addStore/addStore'
// 引入 提示信息
import Alert from '../../components/alert/alert'
// 图片引入方式， 再进行打包时会因为查找不到图片从而报错
//  使用引入，并且赋值给属性的方式可以 进行切换使用
import srcB from './image/heart_128px_1137876_easyicon.net.png'
import srcH from './image/heart_354px_1137663_easyicon.net.png'
export default {
  components: { Alert, AddStore },
  data () {
    return {
      isOpactiy: 0,
      isOpactiyBck: 0,
      stockImg: srcB,
      // alrt 显示或隐藏
      isShowAlert: false,
      // alert 的文字
      alertText: '收藏成功'
    }
  },
  methods: {
    changLi () {
      this.isOpactiy = this.isOpactiy === 0 ? 1 : 0
      this.isOpactiyBck = this.isOpactiyBck === 0 ? 0.5 : 0
    },
    addStock () {
      this.stockImg = this.stockImg === srcB ? srcH : srcB
      this.alertText = this.stockImg === srcB ? '取消收藏' : '收藏成功'
      // // 弹出层显示
      this.isShowAlert = true
      // // 添加动画
      // 获取内层的 alert 设置样式
      this.$refs.outerAlert.$refs.alert.className = 'animation'
    },
    // 更改子级显示与否
    changAlertShow () {
      this.isShowAlert = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.content-outer
  background #F2F2F2
  .content
    width 1200px
    margin 0 auto
    li
      width 380px
      background #F2F2F2
      transition all 0.3s
      position relative
      &:hover
        background white
      img
        width 100%
        height 190px
      #mask
        position absolute
        width 100%
        height 190px
        left 0
        top 0
        background black
        transition all 0.3s
      &>div
        p
          padding 0 20px
          font-weight 500
        .activityName
          font-size 16px
          color #333
          margin-left 0
          overflow hidden
          text-overflow ellipsis
          white-space nowrap
        .activityTime
          margin 10px 0
          width 100%
          display flex
          font-size 14px
          color #999
          justify-content space-between
          align-items center
          div
            align-items center
            display flex
            .greenLeft
              height 0
              width 0
              border solid 12px #2eb000
              border-color transparent #2eb000 transparent transparent
            .greenRight
              text-align center
              line-height 24px
              float left
              height 24px
              line-height 24px
              color #fff
              font-size 12px
              background #2eb000
              width 56px
              margin-right 20px
              border-radius 0 5px 5px 0
              padding-left 5px
        .actvityDescribe
          display block
          white-space nowrap
          overflow hidden
          text-overflow ellipsis
          padding 0 20px
          font-size 12px
          color 0.999
          font-weight 500
          margin-bottom 16px
        .Footer
          border-top 1px #DCDCDC solid
          display flex
          height 60px
          justify-content space-between
          align-content center
          img
            width 25px
            height 25px
        .footer-left
          display flex
          width 100px
          height 100%
          justify-content space-between
          margin-left 20px
          align-items center
          span
            height 20px
          img
            overflow hidden
            border-radius 50%
        .footer-right
          // transition all 0.4s
          margin-right 20px
          display flex
          justify-content space-between
          align-items center
          width 100px
          justify-content space-between
          transition all 0.4s
          button
            all unset
            font-size 12px
            color #fff
            width 50px
            height 26px
            border-radius 3px
            text-align center
            line-height 26px
            background red
            float right
            cursor pointer
</style>
