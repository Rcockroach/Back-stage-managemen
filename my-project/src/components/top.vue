<template>
  <div>
   <div class="header" :style="{background:nowTheme}">
     <h1>LOGO</h1>
     <div class="user">
        <el-dropdown trigger="click">
          <span class="el-dropdown-link">
            <dfn class="userImg">
              <img src="../../static/images/userImg.png" alt="">
            </dfn>
            <i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>修改密码</el-dropdown-item>
            <el-dropdown-item>退出登录</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
     </div>
     <div class="theme">
       <el-dropdown trigger="click">
          <span class="el-dropdown-link">
            <i class="el-icon-star-on el-icon--right"></i>
            主题
          </span>
          <el-dropdown-menu slot="dropdown" class="theme_list">
            <el-dropdown-item disabled>后台主题</el-dropdown-item>
            <el-dropdown-item>
              <div class="colorBox" v-for="(item,index) in theme" :style="{background:item}" :key=index  @click="click_theme(index)"></div>
            </el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
     </div>
   </div>
  </div>
</template>
<script>
export default {
  data(){
    return {
      nowTheme:'#283443',
      theme:[
        '#283443',
        '#368ee0',
        '#e51400',
        '#8cbf26',
      ],
    }
  },
  methods:{
    click_theme(index){
      this.nowTheme = this.theme[index];
    }
  }
}
</script>
<style lang="less" scoped>
  .header{
    width: 90%;
    height: 60px;
    padding: 0 5%;
    z-index: 99;
    color: #fff;
    line-height: 60px;
    position: relative;
    background: #283443;
    h1{
      float: left;
    }
    >div{
      float: right;
      height: 60px;
      margin-left: 20px;
    }
  }
  .el-dropdown-link{
    cursor: pointer;
    color: #fff;
    height: 60px;
    dfn{
      display: inline-block;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      overflow: hidden;
      margin-top: 10px;
      img{
        width: 100%;
      }
    }
    i{
      display: inline-block;
      vertical-align: top;
      font-size: 14px;
      margin-top: 23px;
    }
  }
  .el-dropdown{
    height: 60px;
  }
  .colorBox{
    width: 40px;
    height: 40px;
    float: left;
    margin: 5px;
  }
  .theme_list{
    max-width: 100;
  }
</style>


