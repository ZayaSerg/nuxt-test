<template>
  <div class="content-forgot-password">
    <div class="wrapper">
      <h1>TRAUD</h1>
      <h5>Enter email and we send you a password reset link</h5>
      <el-input 
        v-model="email" 
        placeholder="Email" />
      <el-button type="primary">Send request</el-button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    email: ''
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
  /* margin-bottom: 30px; */
  color: #7e7e7e;
  padding: 0 10px;
}

.el-input {
  margin: 30px 0;
}

.content-forgot-password {
  height: 100%;
  display: flex;
}

.wrapper {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
}
</style>
