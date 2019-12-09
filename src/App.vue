<template>
  <div>
    <Header/>
    <Nav/>
    <Footer/>
  </div>
</template>
<script>
import Header from './components/Header/Header.vue'
import Nav from './components/Nav/Nav.vue'
import Footer from './components/Footer/Footer.vue'
export default {
  name: 'App',
  components:{
    Header,
    Nav,
    Footer
  }
}
</script>
<style lang='stylus' rel='stylesheet/stylus'></style>
