<template>
  <div class="content-signup">
    <div class="wrapper">
      <h1>TRAUD</h1>
      <h5>Please complete to create your account.</h5>
      <div class="full-name">
        <el-input 
          v-model="firstname" 
          class="margin-first"
          placeholder="First name" />
        <el-input 
          v-model="lastname" 
          placeholder="Last name" />
      </div>
      <el-input 
        v-model="username" 
        placeholder="Username" />
      <el-input 
        v-model="email" 
        placeholder="Email" />
      <el-input 
        v-model="password" 
        placeholder="Password" />
      <el-input 
        v-model="confirmpassword" 
        placeholder="Confirm Password"/>
      <el-checkbox v-model="checked">Remember me</el-checkbox>
      <el-button type="primary">Sign Up</el-button>
      <span><a href="">Already have an account? Sign in.</a></span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstname: '',
      lastname: '',
      username: '',
      email: '',
      password: '',
      confirmpassword: '',
      checked: false
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
  margin-top: 10px;
}

.el-input {
  margin-top: 10px;
}

.el-checkbox {
  text-align: left;
  margin: 20px;
}

.content-signup {
  height: 100%;
  display: flex;
}

.wrapper {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
}

.full-name {
  display: flex;
}

.margin-first {
  margin-right: 20px;
}
</style>
