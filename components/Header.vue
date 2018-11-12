<template>
  <header>
    <div class="header">
      <el-menu
        style="width: 100%; display: flex; justify-content: flex-start;"
        class="el-menu-demo"
        mode="horizontal">
        <el-menu-item index="1">Processing Center</el-menu-item>
        <el-menu-item index="2">Processing Center</el-menu-item>
        <el-menu-item index="3">
          <a
            href="https://www.ele.me"
            target="_blank">Orders</a>
        </el-menu-item>
      </el-menu>
      <el-menu
        style="width: 100%; display: flex; justify-content: flex-end;"
        class="el-menu-demo"
        mode="horizontal">
        <el-menu-item index="1">Processing Center</el-menu-item>
        <el-menu-item
          index="2"
          disabled>Info</el-menu-item>
        <el-menu-item index="3">
          <a
            href="https://www.ele.me"
            target="_blank">Orders</a>
        </el-menu-item>
        <el-submenu index="4">
          <template slot="title">Workspace</template>
          <el-menu-item index="2-1">item one</el-menu-item>
          <el-menu-item index="2-2">item two</el-menu-item>
          <el-menu-item index="2-3">item three</el-menu-item>
        </el-submenu>
      </el-menu>
    </div>
  </header>
</template>

<style scoped>
.header {
  display: flex;
}
</style>
