<template>
  <div class="box">
    <!-- 导航 -->
    <nav class="navbar navbar-default" role="navigation">
      <div class="container">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle" data-toggle="collapse"
                  data-target="#example-navbar-collapse">
            <span class="sr-only"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="#"><img class="img-responsive" src="/templates/qqnew/images/logo.jpg" alt=""></a>
        </div>
        <div class="collapse navbar-collapse" id="example-navbar-collapse">
          <ul class="nav navbar-nav">
            <li   class="active" ><a href="/">原创作品</a></li>
            <!--li ><a href="http://shi.wangluoyihao.com/web_list_0_0_3_0_0.aspx" target="_blank">十元模板区</a></li-->
            <li ><a href="/wenti_show_724.aspx">速成教程</a></li>
            <!--li ><a href="/web_list_33.aspx">网页模板</a></li-->
            <li ><a href="/wenti_list_32.aspx">常见问题</a></li>
            <li ><a href="/wenti_show_723.aspx">售后服务</a></li>
          </ul>
        </div>
        <div class="search fr"><input id="keywords" name="keywords" type="text" class="search_in"  onkeydown="if(event.keyCode==13){SiteSearch('/search.aspx', '#keywords');return false};"   /><input name="" type="submit" class="search_btn" value="搜一搜"  onclick="SiteSearch('/search.aspx', '#keywords');"/></div>
      </div>
    </nav>

  </div>
</template>

<script>
import store from '@/vuex/store';
import {mapState, mapActions} from 'vuex';

export default {
  name: 'M-Header',
  computed: {
    ...mapState(['userInfo', 'shoppingCart'])
  },
  methods: {
    ...mapActions(['signOut', 'isLogin']),
    changeCity (city) {
      this.city = city;
    },
    goToPay () {
      this.$router.push('/order');
    },
    myInfo () {
      this.$router.push('/home');
    },
    signOutFun () {
      this.signOut();
      this.$router.push('/');
    }
  },
  store
};
</script>

<style lang="less" scoped>
</style>
