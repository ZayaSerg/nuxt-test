<template>
  <div class="content-signin">
    <div class="wrapper">
      <h1>TRAUD</h1>
      <h5>Welcome back! Please login to your account.</h5>
      <el-input 
        v-model="username" 
        placeholder="User name" />
      <el-input 
        v-model="password" 
        placeholder="Password"/>
      <div class="remember-forgot">
        <el-checkbox v-model="checked">Remember me</el-checkbox>
        <span
          @click="goSignUp"
          class="forgot-password">Forgot Password</span>
      </div>
      <div class="login-signup">
        <el-button type="primary">Login</el-button>
        <el-button>Sign Up</el-button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      password: '',
      checked: false
    }
  },
  computed: {
    goSignUp: function() {
      this.$emit('parentAuth', 'SignUp')
    }
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
}

h1 {
  margin-bottom: 15px;
  color: #444;
}

h5 {
  margin-bottom: 30px;
  color: #7e7e7e;
  padding: 0 10px;
}

span {
  font-size: 12px;
  margin-bottom: 10px;
}

.el-input {
  margin-top: 10px;
}

.el-button {
  min-width: 130px;
}

.content-signin {
  height: 100%;
  display: flex;
}

.wrapper {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
}

.remember-forgot {
  margin: 30px 0;
  display: flex;
  justify-content: space-between;
}

.forgot-password {
  color: #409eff;
  display: inline-block;
  line-height: 19px;
  font-size: 14px;
  font-weight: 500;
}

.login-signup {
  display: flex;
  justify-content: space-between;
}
</style>
