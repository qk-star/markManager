<template>
  <div class="login-wrap">
    <el-form label-position="top"
             label-width="80px"
             :model="formdata"
             class="login-form">
      <h2>用户登录</h2>
      <el-form-item label="用户名">
        <el-input v-model="formdata.username"></el-input>
      </el-form-item>
      <el-form-item label="密码">
        <el-input v-model="formdata.password"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary"
                   @click.prevent="handleLogin"
                   class="login-button">登录</el-button>
      </el-form-item>
    </el-form>

  </div>
</template>
<script>
export default {
  data () {
    return {
      formdata: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    handleLogin () {
      this.$http.post('login', this.formdata).then(res => {
        const { meta: { msg, status } } = res.data
        // 登录成功
        if (status === 200) {
          // 跳转home
          setTimeout(() => {
            this.$router.push({ name: 'home' })
          }, 2000)
          // 提示成功
          this.$message.success(msg)
        } else {
          // 不成功
          // 1.提示消息
          this.$message.error(msg)
        }
      })
    }
  }
}
</script>

<style scoped>
.login-wrap {
  height: 100%;
  background-color: #324152;
  display: flex;
  justify-content: center;
  align-items: center;
}

.login-wrap .login-form {
  width: 400px;
  background-color: #fff;
  border-radius: 5px;
  padding: 30px;
}
.login-form .login-button {
  width: 100%;
}
</style>
