<template>
  <div class="app">
    <router-view />
  </div>
</template>

<style>
html,
body,
#app {
  width: 100%;
  height: 100%;
  margin: 0;
  padding: 0;
  background-color: #f6f7f8;
}

.el-menu--collapse .el-menu .el-submenu,
.el-menu--popup {
  min-width: 140px !important;
}
</style>
