<template>
  <el-row class="main-page">
    <el-col :span="4" class="main-el-row">
      <el-menu
        default-active="1"
        mode="horizontal"
        class="main-nav-page"
        background-color="#08274f"
        text-color="#fff"
        active-text-color="#ffd04b">
        <template>
          <el-menu-item :index="menuItem.id" v-for="menuItem in menuList" :key="menuItem.id">
            <span slot="title" @click="selectMenu(menuItem.url)">{{menuItem.menuName}}</span>
          </el-menu-item>
        </template>
      </el-menu>
    </el-col>
    <el-col :span="20" class="main-el-row">
      <div class="main-con-page">
        adfasd
      </div>
    </el-col>
  </el-row>
</template>
<script>
import { menuList } from './url'
console.log(menuList, 506)
console.log(menuList[0], 156)
console.log(menuList[0].id, 56)
export default {
  data () {
    return {
      menuList: menuList
    }
  },
  components: {
  },
  methods: {
    selectMenu (url) {
      console.log(url, 23)
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
    }
    .main-con-page{
      background: #666;
      height: 100%;
    }
  }
</style>
