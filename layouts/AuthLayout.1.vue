<template>
  <div class="container">
    <!-- <div class="image" /> -->
    <div class="image" />
    <div class="content">
      <component 
        :is="componentName"
        transition="switch" />
      <el-checkbox v-model="loadfirst">Term of use. Privacy policy</el-checkbox>
      <!-- <span>Term of use. Privacy policy</span> -->
    </div>
  </div>
</template>

<script>
import SignIn from '@/components/auth/SignIn'
import SignUp from '@/components/auth/SignUp'
import ForgotPassword from '@/components/auth/ForgotPassword'

export default {
  data() {
    return {
      loadfirst: true
    }
  },
  computed: {
    componentName() {
      let name = this.loadfirst ? 'SignIn' : 'SignUp'
      return () => import(`@/components/auth/${name}`)
    }
  }
}
</script>

<style scoped>
a {
  margin-right: 20px;
  color: white;
}
.el-checkbox {
  margin-bottom: 10px;
}

.container {
  height: 100vh;
  display: flex;
}
.image {
  flex-basis: 50%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  /* background: linear-gradient(45deg, #5a55aa, #242348); */
  background: url(./../static/image.svg) center;
  background-size: cover;
}

.content {
  flex-basis: 50%;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  text-align: center;
}

.switch-transition {
  transition: all 0.5s ease-in-out;
}

.switch-enter {
  left: 100%;
}

.switch-leave {
  left: -100%;
}
</style>
