<template>
  <nav>
    <h1 class="title">
      TRAUD
    </h1>
    <el-row class="tac">
      <el-col :span="12">
        <el-menu
          default-active="2"
          class="el-menu-vertical-demo"
          @open="handleOpen"
          @close="handleClose">
          <el-menu-item index="1">
            <i class="el-icon-view"/>
            <span><nuxt-link to="/MainPage">Main Page</nuxt-link></span>
          </el-menu-item>
          <el-menu-item index="2">
            <i class="el-icon-menu"/>
            <span><nuxt-link to="/Documents">Documents</nuxt-link></span>
          </el-menu-item>
          <el-menu-item index="3">
            <i class="el-icon-goods"/>
            <span><nuxt-link to="/ProductsServices">Products & Services</nuxt-link></span>
          </el-menu-item>
          <el-submenu index="4">
            <template slot="title">
              <i class="el-icon-setting"/>
              <span>Company</span>
            </template>
            <el-menu-item-group title="Group One">
              <el-menu-item index="1-1">Setting</el-menu-item>
              <el-menu-item index="1-2">Staff</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="Group Two">
              <el-menu-item index="1-3">Shops</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">Account</template>
              <el-menu-item index="1-4-1">Discount</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="5">
            <template slot="title">
              <i class="el-icon-location"/>
              <span>Contractors</span>
            </template>
            <el-menu-item index="1-1">Suppliers</el-menu-item>
            <el-menu-item index="1-2">Clients</el-menu-item>
          </el-submenu>
          <el-menu-item
            index="6"
            disabled>
            <i class="el-icon-document"/>
            <span>Plans & Pricing</span>
          </el-menu-item>
          <el-menu-item index="7">
            <i class="el-icon-setting"/>
            <span><nuxt-link to="/Auth">Trash</nuxt-link></span>
          </el-menu-item>
        </el-menu>
      </el-col>
    </el-row>

    <!-- <nav>
      <ul>
        <li><nuxt-link to="/">Starting Page</nuxt-link></li>
        <li><nuxt-link to="/recipes">Recipe</nuxt-link></li>
        <li><nuxt-link to="/about">About</nuxt-link></li>
      </ul>
    </nav> -->
  </nav>
</template>

<script>
export default {
  data() {
    return {
      isCollapse: true
    }
  },
  methods: {
    handleOpen(key, keyPath) {
      console.log(key, keyPath)
    },
    handleClose(key, keyPath) {
      console.log(key, keyPath)
    }
  }
}
</script>

<style scoped>
.el-menu-vertical-demo:not(.el-menu--collapse) {
  width: 200px;
  /* min-height: 400px; */
  max-height: 100%;
}
/* .el-row {
  max-height: 100vh;
} */

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 60px;
  color: #35495e;
  letter-spacing: 1px;
}

a {
  text-decoration: none;
  color: #909399;
}

a:active {
  color: #909399;
}
</style>
