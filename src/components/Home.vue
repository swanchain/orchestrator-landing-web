<template>
  <div class="wrapper" id="wrapper" ref="area">
    <el-container>
      <el-header>
        <v-head></v-head>
      </el-header>
      <el-main>
        <div class="content">
          <router-view v-slot="{ Component }">
            <transition name="move" mode="out-in">
              <keep-alive>
                <component :is="Component" />
              </keep-alive>
            </transition>
          </router-view>
          <el-backtop :right="20" :bottom="20" />
        </div>
      </el-main>
      <el-footer>
        <v-foot></v-foot>
      </el-footer>
    </el-container>
  </div>
</template>

<script>
import vHead from './Header.vue';
import vFoot from './Footer.vue';
import { defineComponent, computed, onMounted, watch, ref, reactive, getCurrentInstance } from 'vue'
import { useStore } from "vuex"
import { useRouter, useRoute } from 'vue-router'
import { ElBacktop, ElContainer, ElHeader, ElFooter, ElMain } from "element-plus"
export default defineComponent({
  setup () {
    const store = useStore()
    const bodyWidth = ref(document.body.clientWidth < 992)
    const system = getCurrentInstance().appContext.config.globalProperties
    const route = useRoute()
    const router = useRouter()

    onMounted(() => { })
    return {}
  },
  components: {
    vFoot, vHead,
    ElBacktop, ElContainer, ElHeader, ElFooter, ElMain
  }
})
</script>

<style lang="less" scoped>
.wrapper {
  min-height: 100vh;
  .content {
    .el-backtop {
      width: 30px;
      height: 30px;
      background-color: #ffffff;
      color: #7c2d8a;
      z-index: 99;
    }
    .el-backtop__icon {
      font-size: 16px;
    }
  }
  .el-container {
    padding: 0 0 0.5rem;
    .el-header {
      background-color: #171a0d;
      border-bottom: 1px solid #181a0d;
    }
    .el-main {
      padding: 0;
      overflow: hidden;
    }
    .el-header,
    .el-footer {
      height: auto;
      padding: 0;
    }
  }
}
</style>

<style lang="less">
.mt-border {
  margin: 0.3rem auto;
  border-top: 1px solid #8c878d;
}
.lang-max {
  width: 71%;
  max-width: 1360px;
  padding: 0;
  margin: auto;
  overflow: hidden;
  @media screen and (min-width: 1800px) {
    width: 100%;
    max-width: 1460px;
  }
  @media screen and (min-width: 1920px) {
    width: 100%;
    max-width: 1520px;
  }
  @media screen and (min-width: 2160px) {
    width: 100%;
    max-width: 1680px;
  }
  @media screen and (min-width: 2200px) {
    max-width: 1920px;
  }
  @media screen and (min-width: 2853px) {
    max-width: 2160px;
  }
  @media screen and (min-width: 3804px) {
    max-width: 2366px;
  }
  @media screen and (min-width: 4090px) {
    max-width: 2853px;
  }
  @media screen and (min-width: 5120px) {
    max-width: 3804px;
  }
  @media screen and (max-width: 1200px) {
    width: calc(100% - 64px);
    padding: 0 32px;
  }
  @media screen and (max-width: 600px) {
    width: calc(100% - 32px);
    padding: 0 16px;
  }
}
.describe {
  font-size: 0.14rem;
  // @media screen and (max-width: 600px) {
  //   font-size: 12px;
  // }
  a {
    color: #447dff;
    &:hover {
      text-decoration: underline;
    }
  }
}

.flex-row {
  display: flex;
  align-items: center;
}
</style>

