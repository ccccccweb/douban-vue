<template>
  <div id="app" v-cloak>
    <!--<img src="./assets/logo.png">-->
    <router-view></router-view>
    <TabbarWrap></TabbarWrap>
  </div>
</template>
<script>
  import TabbarWrap from './components/TabbarWrap'
  import "./assets/libs/jquery-1.11.3.min.js"
  export default {
    name: 'app',
    components:{
      TabbarWrap
    },
    mounted:function () {
      $(function () {
        var html = $('html');
        var deviceW = $(window).width();
        if (deviceW >= 540) {
          html.css({'font-size': '54px'});
        } else {
          html.css({'font-size': deviceW / 10 + 'px'});
        }
        $(window).resize(function () {
          var deviceW = $(window).width();
          if (deviceW >= 540) {
            html.css({'font-size': '54px'});
          } else {
            html.css({'font-size': deviceW / 10 + 'px'});
          }
        });
      });
    },
    created:function () {
      this.$router.push('/Home')
    }
  }
</script>
<style>
  *{padding:0;margin:0;}
  body{font-size: 16px;}
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    background-color: #f8f8f8;
    padding-bottom: 49px;
  }
</style>
