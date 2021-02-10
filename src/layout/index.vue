<template>
  <div>
    <sidebar class="sidebar-container" :isCollapse="isCollapse"/>
    <div class="main-container">
      <navbar :isActive="isCollapse" @sl="sl"/>
    </div>
  </div>
</template>

<script>
import { Navbar, Sidebar } from './components'

export default {
  name: 'index',
  data () {
    return {
      isCollapse: false
    }
  },
  components: {
    Navbar,
    Sidebar
  },
  methods: {
    sl: function () {
      this.isCollapse = !this.isCollapse
    }
  }
}
</script>

<style scoped>
.main-container {
  min-height: 100%;
  transition: margin-left .28s;
  margin-left: 200px;
  position: relative;
}

.sidebar-container {
  transition: width 0.28s;
  width:200px !important;
  background-color: #2c3e50;
  height: 100%;
  position: fixed;
  font-size: 0px;
  top: 0;
  bottom: 0;
  left: 0;
  z-index: 1001;
  overflow: hidden;
}

.scrollbar-wrapper {
  overflow-x: hidden !important;
}

.el-scrollbar__bar.is-vertical {
  right: 0px;
}

.el-scrollbar {
  height: 100%;
}

.el-scrollbar {
  height: calc(100% - 50px);
}

.is-horizontal {
  display: none;
}

a {
  display: inline-block;
  width: 100%;
  overflow: hidden;
}

.svg-icon {
  margin-right: 16px;
}

.sub-el-icon {
  margin-right: 12px;
  margin-left: -2px;
}

.el-menu {
  border: none;
  height: 100%;
  width: 100% !important;
}
</style>
