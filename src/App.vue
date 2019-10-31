<template>
  <div id="app">
    <el-container style=" border: 1px solid #eee">
      <el-aside width="300px" style="background-color: rgb(238, 241, 246); height: 100vh">
        <el-menu
          router
          :default-openeds="['1']"
        >
          <el-submenu index="1">
            <el-menu-item index="/" route="/">
              Home
            </el-menu-item>
            <el-menu-item index="/about" route="/about">
              About
            </el-menu-item>
          </el-submenu>
        </el-menu>
      </el-aside>
      <el-main>
        <transition name="slide">
          <router-view/>
        </transition>
      </el-main>
    </el-container>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
