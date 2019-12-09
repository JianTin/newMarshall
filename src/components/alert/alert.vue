<template>
  <div>
    <div id="alert"
         ref="alert"
         v-show="isShowAlert"> {{alertText}}</div>
  </div>
</template>

<script>
export default {
  props: ['isShowAlert', 'changAlertShow', 'alertText'],
  mounted () {
    this.$refs.alert.addEventListener('webkitAnimationEnd', () => {
      this.$refs.alert.classList.remove('animation')
      // 更改 为 隐藏
      this.changAlertShow()
    })
  },
  beforeUpdate () {
    console.log(this.isShowAlert)
  }
}
</script>

<style lang="stylus" scoped>
@keyframes animat
  0%
    height 0px
  40%
    height 70px
  70%
    height 70px
  100%
    height 0px
#alert
  width 100%
  background rgb(217, 0, 0)
  position fixed
  z-index 10
  top 0
  font-size 18px
  color white
  text-align center
  line-height 70px
  overflow hidden
  &.animation
    animation animat 1.3s forwards
</style>
