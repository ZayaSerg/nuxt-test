<template>
  <div class="container">
    <div class="image" />
    <div class="content">
      <component 
        :is="componentName"
        @loadingViewSignIn="onCurrentView"
        @loadingViewSignUp="onCurrentView"
        @loadingViewForgotPassword="onCurrentView" />
      <span>Term of use. Privacy policy</span>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentView: 'SignIn'
    }
  },
  computed: {
    componentName() {
      let name = this.currentView
      return () => import(`@/components/auth/${name}`)
    }
  },
  methods: {
    onCurrentView(data) {
      this.currentView = data.loadingView
    }
  }
}
</script>

<style scoped>
span {
  margin-bottom: 10px;
  color: #606266;
  /* color: #409eff; */
  display: inline-block;
  line-height: 19px;
  font-size: 14px;
  font-weight: 500;
  cursor: pointer;
}

.container {
  height: 100vh;
  display: flex;
}
.image {
  flex-basis: 50%;
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
</style>
