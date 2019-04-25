<template>
  <div id="app">
    <el-container class="container">
      <el-header>
        <div class="nav">DTOS集装箱堆场管理系统</div>
      </el-header>
      <el-container>
        <el-aside style="width: 200px;">
          <el-row class="tac">
            <el-col>
              <el-menu
                default-active="1"
                class="el-menu-vertical-demo"
                background-color="white"
                text-color="black"
                active-text-color="#ffc0cb"
              >
                <el-menu-item index="1" @click="changedyxq">
                  <i class="el-icon-location"></i>
                  <span slot="title">定义箱区</span>
                </el-menu-item>
                <el-menu-item index="2" @click="changezcinfo">
                  <i class="el-icon-menu"></i>
                  <span slot="title">集装箱在场信息</span>
                </el-menu-item>
                <el-menu-item index="3" @click="changejclist">
                  <i class="el-icon-document"></i>
                  <span slot="title">集装箱进场清单</span>
                </el-menu-item>
              </el-menu>
            </el-col>
          </el-row>
        </el-aside>
        <el-main>
          <dyxq v-if="xq"></dyxq>
          <div v-if="zcinfo"></div>
          <div v-if="jclist"></div>
        </el-main>
      </el-container>
    </el-container>
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import dyxq from "./components/dyxq.vue";

export default {
  name: "app",
  components: {
    HelloWorld,
    dyxq
  },
  data() {
    return {
      xq: true,
      zcinfo: false,
      jclist: false
    };
  },
  methods: {
    changedyxq() {
      if (!this.xq) {
        this.xq = true;
        this.zcinfo = false;
        this.jclist = false;
      }
    },
    changezcinfo() {
      if (!this.zcinfo) {
        this.zcinfo = true;
        this.xq = false;
      }
    },
    changejclist() {
      if (!this.jclist) {
        this.jclist = true;
        this.xq = false;
      }
    }
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}

.nav {
  width: 100%;
  height: 80px;
  background: #ffc0cb;
  font-size: 50px;
  font-weight: bold;
  color: white;
}

.container {
  width: 100%;
  height: auto;
}

.el-aside {
  height: 503px;
  position: absolute;
  top: 88px;
  background: white;
  left: 28px;
  border-right: 1px solid #e6e6e6;
  border-left: 1px solid #e6e6e6;
}

.el-menu {
  border-right: none !important;
  text-align: justify;
}

.el-menu-item:focus,
.el-menu-item:hover {
  background-color: #ecf5ff !important;
}

.el-main {
  margin-left: 150px;
}
</style>
