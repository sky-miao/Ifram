<template>
  <el-row class="main-page">
    <el-col :xs="0" :span="2" class="main-el-row">
      <el-menu
        default-active="1"
        class="main-nav-page"
        background-color="#05172f"
        text-color="#fff"
        active-text-color="#ffd04b">
        <template>
          <el-menu-item>
            <img src="../assets/imgs/logo.png" alt="logo">
          </el-menu-item>
          <el-menu-item :index="menuItem.id" v-for="menuItem in menuList" :key="menuItem.id">
            <span class="item" slot="title" @click="selectMenu(menuItem.url)">{{menuItem.menuName}}</span>
          </el-menu-item>
        </template>
      </el-menu>
    </el-col>
    <el-col :xs="24" :lg="0" class="main-el-row-sm">
      <img src="../assets/imgs/logo.png" alt="logo">
      <span class="sm-nav-wrap">
        <img v-if="menuVisible === false" @click="clickMenu" src="../assets/imgs/nav.png"/>
        <i v-else @click="clickMenu" class="el-icon-close"></i>
      </span>
    </el-col>
    <ul v-show="menuVisible" class="nav-ul-wrap">
      <li :index="menuItem.id" v-for="menuItem in menuList" :key="menuItem.id">
        <span class="item" slot="title" @click="selectMenu(menuItem.url)">{{menuItem.menuName}}</span>
      </li>
    </ul>
    <el-col :xs="24" :span="22" class="main-el-row">
      <div class="main-con-page">
        <iframe style="width: 100%; height: 99%" :src="url"></iframe>
      </div>
    </el-col>
  </el-row>
</template>
<script>
import { menuList } from './url'
export default {
  data () {
    return {
      menuVisible: false,
      menuList: menuList,
      url: 'http://localhost:3001/#/'
    }
  },
  components: {
  },
  methods: {
    selectMenu (url) {
      this.url = url
    },
    clickMenu () {
      this.menuVisible = !this.menuVisible
    }
  }
}
</script>
<style lang="less">
  .main-page{
    height: 100%;
    .main-el-row{
      height: 100%;
    }
    .main-nav-page{
      background: #ddd;
      height: 100%;
      min-width: 150px;
      border-right: none;
      .item{
        display: inline-block;
        width: 100%;
      }
    }
    .main-el-row-sm{
      position: relative;
      background: #ddd;
      height: 40px;
      img{
        position: absolute;
        top: 50%;
        left: 20px;
        transform: translateY(-50%);
      }
      .sm-nav-wrap{
        position: absolute;
        top: 50%;
        right: 20px;
        transform: translateY(-50%);
      }
    }
    .nav-ul-wrap{
      background: #333;
      li{
        border-bottom: 1px solid #ddd;
      }
      .item{
        display: inline-block;
        width: 100%;
      }
    }
    .main-con-page{
      background: #666;
      height: 100%;
    }
  }
</style>
