<template>
  <el-container class="container">
    <el-header class="header">
      <el-row>
        <el-col :span="4"
                class="header-logo">
          <div class="grid-content bg-purple">
            <img src="../../assets/images/logo.png"
                 alt="无法显示图片">
          </div>
        </el-col>
        <el-col :span="16"
                class="middle">
          <h3>电商后台管理系统</h3>
        </el-col>
        <el-col :span="4">
          <div class="grid-content bg-purple">
            <a href="#"
               class="loginout">退出</a>
          </div>
        </el-col>
      </el-row>
    </el-header>
    <el-container>
      <el-aside width="200px"
                class="aside">Aside</el-aside>
      <el-main class="main">Main</el-main>
    </el-container>
  </el-container>
</template>
<script>
export default {
  data () {
    return {}
  }
}
</script>
<style  scoped>
.container {
  height: 100%;
  min-width: 700px;
}
.header {
  background-color: #879cb3;
}
.aside {
  background-color: #a5b5c5;
}
.main {
  background-color: #e9eef3;
  height: 100%;
}
/* 头部样式 */
.header-logo img {
  height: 45px;
  position: relative;
  top: 7.5px;
}
.middle {
  text-align: center;
}
.loginout {
  line-height: 60px;
  text-decoration: none;
  color: #fff;
  position: relative;
  right: -40px;
}
</style>
