<template>
  <div class="box">
    <div class="container">
      <div class="navbar-header"></div>
      <div class="navbar-collapse">
        <ul>
          <li>
            <router-link to="/">网站导航</router-link>
          </li>
          <li>
            <router-link to="/freeback">意见反馈</router-link>
          </li>
          <li>
            <router-link to="/">商城首页</router-link>
          </li>
        </ul>
      </div>
      <div class="search fr"></div>
    </div>
  </div>
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
  .box {
    margin-bottom: 0px;
    background: #2a5abe;
    height: 58px;
    .container {
      padding: 0px;
      ul {
        list-style: none;
        li {
          float: left;
          font-size: 14px;
          line-height: 55px;
          margin-right: 15px;
        }
      }
      a {
        text-decoration: none;
        color: #999999;
        padding-left: 15px;
        border-left: 1px solid #ccc;
        cursor: pointer;
      }
    }
  }
</style>
